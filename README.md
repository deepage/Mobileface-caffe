# Mobileface-caffe

根据月生大佬的文章和训练指点，使用他的网络结构以及峰神的AM-softmax loss在CASIA-WEB数据集上进行训练，solver和model都已经上传了，log因为被覆盖了所以无法提供。上传的模型在LFW上可以达到99.28%，和论文精度一致，或许可以再进一步，暂时在训练MS-celeb-1M了，所以没有时间继续训CASIA-WEB,有兴趣的可以自己试试。

对于训练的一点说明，因为我只有单卡1060，所以batch_size设的比较小，采用在solver中加入iter_size来达到batch_size512的目的，先使用softmax训差不多1W次，然后再换AM接着训练，这样可以收敛的快一些，月生大佬论文中说的是迭代max_size为6W次，我在用AM训的时候发现5W和5W5收敛结果更好，所以选择这个结果上传，应该是AM和arc有区别导致。



paper:[MobileFaceNets: Efficient CNNs for Accurate Real-time Face Verification on Mobile Devices](https://arxiv.org/abs/1804.07573)

amsoftmax:[happynear/AMSoftmax](https://github.com/happynear/AMSoftmax)

depthwise convolution:[yonghenglh6/DepthwiseConvolution](https://github.com/yonghenglh6/DepthwiseConvolution)

mobilenetv2-caffe:[shicai/MobileNet-Caffe](https://github.com/shicai/MobileNet-Caffe)
