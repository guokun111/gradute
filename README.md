# gradute
毕业设计准备
```
class Net(nn.Module):
    def __init__(self):
        nn.Module.__init__(self)
        self.conv2d = nn.Conv2d(in_channels=3,out_channels=64,kernel_size=4,stride=2,padding=1)
 
    def forward(self, x):
        print(x.requires_grad)
        x = self.conv2d(x)
        return x
print(net.conv2d.weight)         
print(net.conv2d.bias)
```
卷积层最重要的可学习参数——权重参数和偏置参数去哪了？在Tensorflow中都是先定义好weight和bias，再去定义卷积层的呀！别担心，在Pytorch的nn模块中，它是不需要你手动定义网络层的权重和偏置的，这也是体现Pytorch使用简便的地方。当然，如果有小伙伴适应不了这种不定义权重和偏置的方法，Pytorch还提供了nn.Functional函数式编程的方法，其中的F.conv2d()就和Tensorflow一样，要先定义好卷积核的权重和偏置，作为F.conv2d（）的形参之一。
  回到nn.Conv2d上来，我们可以通过实例名.weight和实例名.bias来查看卷积层的权重和偏置，如上图所示。还有小伙伴要问了，那么它们是如何初始化的呢？
  首先给结论，在nn模块中，Pytorch对于卷积层的权重和偏置（如果需要偏置）初始化都是采用He初始化的，因为它非常适合于ReLU函数。这一点大家看Pytorch的nn模块中卷积层的源码实现就能清楚地发现了，当然，我们也可以重新对权重等参数进行其他的初始化，可以查看其他教程，此处不再多言。


————————————————
版权声明：本文为CSDN博主「风雪夜归人o」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/qq_42079689/article/details/102642610
