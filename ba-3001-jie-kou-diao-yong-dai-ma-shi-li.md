<pre><code>
using System;
using System.Net;
using System.Net.Http;
using System.Threading.Tasks;
using IdentityModel.Client;
using LoadMaster.Compute.Models;
using Newtonsoft.Json;

namespace LoadMaster.TestApp {
    class Program {
        //要调用的服务地址服务地址
        private const string ServerUrlBase = "https://optimize.zhuangxiang.com/";
        //OpenId 服务地址。
        private const string TokenUrlBase = "https://api.zhuangxiang.com/";
        static void Main (string[] args) {

            while (true)
            {
                RunDemoAsync().Wait();
                var c = Console.ReadKey();
                if (c.KeyChar == 'a')
                    break;
            }
        }

        public static async Task RunDemoAsync () {
            //获取token
            var accessToken = await GetAccessTokenViaOwnerPasswordAsync();
            //调用服务
            await DoLoadingOptimizeAsync (accessToken);
        }

        private static async Task DoLoadingOptimizeAsync (string accessToken) {
            OptimizeRequest loadRequest = CreateLoadRequest ();

            var disco = await DiscoveryClient.GetAsync(ServerUrlBase);


            using (var client = new HttpClient ()) {
                client.SetBearerToken(accessToken);

                var requestContent = new StringContent (JsonConvert.SerializeObject (loadRequest), System.Text.Encoding.UTF8, "Application/Json");

                var response = await client.PostAsync ($"{ServerUrlBase}api/LoadingOptimize/DoLoadingOptimize", requestContent);
                if (!response.IsSuccessStatusCode) {
                    Console.WriteLine (response.StatusCode);
                    return;
                }

                var content = await response.Content.ReadAsStringAsync ();
                var planResult = JsonConvert.DeserializeObject<OptimizeResponse> (content);

                Console.WriteLine ();
                Console.WriteLine ("Total PackedUnit count: " + planResult.PackedUnits.Count);
                Console.WriteLine ();
            }
        }

        private static async Task<string> GetAccessTokenViaOwnerPasswordAsync()
        {
            var disco = await DiscoveryClient.GetAsync(TokenUrlBase);

            using (var httpHandler = new HttpClientHandler())
            {
                //在Cookie中设置您的TenantId.
                httpHandler.CookieContainer.Add(new Uri(TokenUrlBase), new Cookie("Abp.TenantId", "1")); //Set TenantId

                //通过您的 appId， appSecret, username, passowrd 获取token。这里设置的值只是要给示例。
                var tokenClient = new TokenClient(disco.TokenEndpoint, "client", "def2edf7-5d42-4edc-a84a-30136c340e13", httpHandler);
                var tokenResponse = await tokenClient.RequestResourceOwnerPasswordAsync("admin", "123456,");

                if (tokenResponse.IsError)
                {
                    Console.WriteLine("Error: ");
                    Console.WriteLine(tokenResponse.Error);
                }

                Console.WriteLine(tokenResponse.Json);

                return tokenResponse.AccessToken;
            }
        }


        private static OptimizeRequest CreateLoadRequest () {

            OptimizeRequest request = new OptimizeRequest ();

            //添加要装栽的货物。
            request.PackingCargoes.Add (new PackingCargoDto {
                Id = Guid.NewGuid (),
                    Name = "cargo1",
                    Length = 1.1f,
                    Width = 0.8f,
                    Height = 0.6f,
                    Weight = 0.5f,
                    Quantity = 99

                    //更多的约束，根据需要设置，不设置将使用默认值。
            });

            //添加可以使用的容器。
            request.PackingContainers.Add (new PackingContainerDto {
                Id = Guid.NewGuid (),
                    Name = "20ft",
                    InnerX = 2.35f,
                    InnerY = 2.38f,
                    InnerZ = 5.89f,
                    Maxload = 21000
            });

            //设置装载规则,更多的规则选项，请查看帮助。
            request.LoadingOptions = new LoadingOptionDto
            {
                ContainerSelectMode = 0
            };

            return request;
        }
    }
}
</code></pre>