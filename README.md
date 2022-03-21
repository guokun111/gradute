# gradute
毕业设计准备
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
————————————————
版权声明：本文为CSDN博主「Akita·wang」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/qq_19168521/article/details/115612529
