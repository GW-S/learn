Mask矩阵：浅谈mask矩阵

参考文献：http://www.linzehui.me/2018/10/12/%E7%A2%8E%E7%89%87%E7%9F%A5%E8%AF%86/%E6%B5%85%E8%B0%88mask%E7%9F%A9%E9%98%B5/

为什么要用mask矩阵？因为mask可以帮我们阻止一些反向传播，即在一些不太合适的情况下，阻止一些操作。

mask的能力，就是mask和对应的tensor维持一个相同的矩阵，mask为0的点和tensor相应位置的值为0，此时，就不能进行反向传播了。

# 情况1:mask乘积为0的点。可以在embedding的时候，防止更新相应的词嵌入。
# 情况2:针对不同的句子长度，用mask把长的屏蔽掉。
# 情况3:在计算loss的时候，可以把为0的loss屏蔽掉，这样就不会更新loss，那么在计算loss的时候，就不会reduce相应的loss.


