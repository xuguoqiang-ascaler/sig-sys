# 简介

本文主要是介绍下在一位情况下的光的衍射图像的分析中傅立叶变换的应用，该理论在利用X光线的衍射图分析晶体的结构中具有重要的作用。

# 夫琅和费衍射(Fraunhofer diffraction)

我们在该文中只关心夫琅和费衍射衍射，这是一种远场衍射。

夫琅和费衍射衍射有以下的假设：
* 光源距离光栅足够远，也就是说是平行光入射光栅，光栅上的所有的点都在波阵面上，没有相位差。
* 光栅与衍射平面的距离远远大于光栅的长度。

# 夫琅和费衍射图案的分析

光是电磁场，但是在为了简化计算，该文中我们只考虑电场。(读者可以按照本文的流程自行推导完整电磁场表达式下的结论)

$$E=E_0e^{2\pi ivt}$$

<div align="center">
<img src=./images/FourierAppInDiffaction/diffraction_gen.jpeg with=340 height=300/>
</div>

在光栅平面上，所有点的相位都是相同的，所以相位的改变只取决于$r$的大小。可以讲光栅分成长度为$dx$的区间的组合，所以在p点，单一的$dx$产生的电场强度是

$$dE=E_0e^{2\pi ivt}e^{2\pi ir/\lambda} dx$$

所有的$dx$的集合在p点产生的电场的强度是

$$E=\int_{apertures}{E_0e^{2\pi ivt}e^{2\pi ir/\lambda}dx}=E_0e^{2\pi ivt}\int_{apertures}{e^{2\pi ir/\lambda}dx}$$

其中，$apertrues$是光栅的区间分布的集合。

<div align="center">
<img src=./images/FourierAppInDiffaction/diffraction_inf.jpeg with=340 height=300/>
</div>

由于我们考虑的是夫琅和费衍射，所以衍射图案的屏幕距离光栅很远，远大于光栅孔径的长度，所以我们有

$$r \gg x$$

在该假设下，我们有

$$r = r_0 - x \sin \theta $$

所以我们进一步得到

$$ E = E_0e^{2 \pi ivt}e^{2 \pi ir_0 \lambda}\int_{apertures}{e^{-2 \pi ix \sin \theta / \lambda}dx} $$

我们简化一下表达式

$$ p = \sin \theta / \lambda $$

$$ E \propto \int_{-\infty}^{+\infty}{A(x)e^{-2\pi ipx}dx} $$

其中的$A(x)$表示$apertures$的区间分布情况。光可以透过的区间设置为1，否则为0。

我们再做进一步的推导

$$ \tan \theta = h / d $$

如果

$$ h \ll d $$

由泰勒展开知

$$ \tan \theta = \theta + \frac{1}{3} \theta^3 + \cdots $$

$$ \sin \theta = \theta - \frac{1}{3!} \theta^3 + \cdots $$

所以

$$ p = \sin \theta / \lambda \propto h $$

所以我们可以看出，衍射图像是光栅图案的傅立叶变换。

# 结论

我们可以看到在一维的情况下，衍射图像是光栅图像做傅立叶变换可得。同理，当我们知道衍射图像，我们也可以通过傅立叶反变换由衍射图像获取光栅图像。如果我们将光栅替换为晶体，光源改为x射线，那么我们可以根据x射线的衍射图获取晶体的结构，当然，这需要多维傅立叶变换和采样理论的推导。
