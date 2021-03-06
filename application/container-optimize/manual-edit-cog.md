# r、如何使用手动编辑调整货物重心

日本专家实验结果，当货柜装载重量接近限重时，长宽方向重心偏移要控制在10%以内；当货柜装载重量小于限重时，长宽方向重心偏移可略超过10%。若软件生成的方案没有达到要求，如何用手动编辑调整货物的重心？

下面通过一个示例来讲解：计算货物装海运集装箱，得出的装载方案如下图：

![](../../.gitbook/assets/0%20%2822%29.png)

在3D图左下角大家可以看到货柜的重量利用率为96.5%，货柜装载重量接近限重，而长度、宽度方向的重心偏移都超出10%的范围，这种情况可以使用手动编辑进行调整。

通过平衡分析的平面图可以看出，长度方向货物重心偏向集装箱前方，需要将前方的重货和后方的轻货互换位置；宽度方向货物重心偏向集装箱左侧，需要将左侧的重货和右侧的轻货互换位置。

点击软件上方的“手动编辑”按钮，进入手动编辑界面。

![](../../.gitbook/assets/1%20%2821%29.png)

首先将前方的重货和后方的轻货互换位置：

1）在最后一行紫色货物，右击鼠标，点击【切割】中的“行切割”。

![](../../.gitbook/assets/2%20%2821%29.png)

2）选中切割出来的最后一行紫色货物，右手按住鼠标左键不放，将货物拽出集装箱。

![](../../.gitbook/assets/3%20%2822%29.png)

3）选中第一行的黄色货物，按住鼠标左键不放，将其拖动并放到集装箱最后一行的位置上，当它靠近其他货物时会跳起，所以在它没有跳起时，左手按住键盘上的“Ctrl”键不放，右手按住鼠标左键将货物拖动到相应位置。

![](../../.gitbook/assets/4%20%2820%29.png)

4）同理将紫色货物放到集装箱的最前面。

![](../../.gitbook/assets/5%20%2818%29.png)

通过右下角重心偏移的实时数据可以看到，长度方向的重心偏移控制在了10%以内，前方的重货和后方的轻货互换位置完成。

![](../../.gitbook/assets/6%20%2816%29.png)

然后将左侧的重货和右侧的轻货互换位置：

1）选中第二行的黄色货物，按住鼠标左键不放，将其拽出集装箱。

![](../../.gitbook/assets/7%20%2813%29.png)

2）选中第二行的紫色货物，左手按住“Ctrl”键不放，右手按住鼠标左键将货物移动集装箱左侧。

![](../../.gitbook/assets/8%20%2810%29.png)

3）选中集装箱外的黄色货物，将它移动到第二行的空隙位置。会发现，即使按住“Ctrl”键不放，也没办法将其放入，这时就要按住“Ctrl”键不放，点击软件下方【移动】中的“左移”，直到货物一部分进到空隙，然后在用鼠标拖动，将其靠紧其他货物且不重合。

![](../../.gitbook/assets/9%20%289%29.png)

通过右下角重心偏移的实时数据可以看到，宽度方向的重心偏移也控制在了10%以内，左侧的重货和右侧的轻货互换位置完成。

![](../../.gitbook/assets/10%20%285%29.png)

本案例手动编辑完成，点击右下角的“保存”按钮，就可以看到手动编辑后的装载方案，

手动编辑其他功能的详情介绍请参考上文《手动编辑》。

手动编辑有下面几个的小技巧：

1）货物线条是红色，代表在货柜外；货物线条是绿色，代表在货柜内。

2）移动货物时：右手按住鼠标左键移动。

3）货物定位时：左手按住ctrl键，右手按住鼠标左键移动，直到定好位置再松手，货物就不会跳起了。

4）组建新装卸块时，左手按住ctrl键，右手点击鼠标，可以选中多个装卸块。

5）点击撤销按钮可以取消当前操作，返回上一步。

最后手动编辑有几个注意事项：

1）手动编辑后的方案，一旦点击自动优化重新计算，则丢失手动编辑后的方案。

2）若无法从货柜内移出货物：这说明键盘的ctrl键失灵了，还在按住不放的状态。请用力敲打下此键再操作。

3）有时因鼠标质量原因，导致不能很好地控制货物的移动，这时可尝试换个鼠标试试。

4）因第一次使用手动编辑功能，比较陌生，初次感觉比较难用，这是正常的。使用上一周就会发现操作非常简便灵活。

