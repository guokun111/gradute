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
