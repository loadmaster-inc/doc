# a、基本装载规则

![](/.gitbook/assets/25.png)1）容器选择方式：选择“自动选择容器组合达到使用容器数据最少的目的”时优化的目标是使容器数量最少；选择“按照费用最小原则选择容器组合来装载货物”时优化的目标是使总费用最少。

2）堆码方式：在选择“自由组合”时，不对货物装载进行限制；在选择“相同制品相邻摆放”时，限制所有相同的货物必须摆放在一起。在选择“仅允许长宽相同的物品相互堆叠”时，限制只有长宽相同的货物才能堆叠在一起。

3）相同制品相邻摆放：要求设计的装载方案，尽可能的使相同的物品放在一起，这样方便现场操作装载和卸货。

![](/.gitbook/assets/28.png)

4）交叉深度：不种货物相邻摆放时产品的互相交叉的最大深度，当值为0时，产品在长度方向不会发生交叉。实际操作，允许适度的交叉可以提高装载效率，同时不会增加装载的复杂度，效果如下图：

![](/.gitbook/assets/26.png)

5）在空间没有充分利用时优先选择平铺：货物较少的时候，填不满集装箱，这样的话在运输过程中可能发生货损，如果将货物平铺在集装箱，将集装箱的底部剩余空间填满，这样能保证货物的安全性。勾选这一选项后会把货物优先填满集装箱的底部。

![](/.gitbook/assets/27.png)

6）最大装卸段长度：  
限制卸段长度是指装柜软件生成方案时，限制装载方案中每一个步骤的装载长度不超过设定的长度，主要是为了方便用装箱时现场人工或叉车的实际操作。比如使用叉车把货物装入集装箱时，叉车每次装入的货物有长度限制，不可能一次性装入长达10米的货物，所以需要限制每次装入货物的长度。勾选“限制装卸段长度”后可以限制每次装入货物的长度，具体的长度在“最大装卸段长度”输入框中设置。

