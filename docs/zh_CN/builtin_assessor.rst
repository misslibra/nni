内置 Assessor
=================

为了节省计算资源，在 NNI 中可通过创建 **Assessor**，来配置提前终止策略。

Assessor 从 Trial 中接收中间结果，并通过指定的算法决定此 Trial 是否应该终止。 一旦 Trial 满足了提前终止策略（这表示 Assessor 认为最终结果不会太好），Assessor 会终止此 Trial，并将其状态标志为 `"EARLY_STOPPED"`。

这是 MNIST 在使用了 'Curvefitting' Assessor 的 'maximize' 模式后的实验结果，可以看到 Assessor 成功的将大量最终结果不好的 Trial **提前结束** 。 使用 Assessor，能在相同的计算资源下，得到更好的结果。

*实现代码：config_assessor.yml <https://github.com/Microsoft/nni/blob/master/examples/trials/mnist-tfv1/config_assessor.yml>*

..  image:: ../img/Assessor.png

..  toctree::
    :maxdepth: 1

    概述<./Assessor/BuiltinAssessor>
    Medianstop<./Assessor/MedianstopAssessor>
    Curvefitting（曲线拟合）<./Assessor/CurvefittingAssessor>