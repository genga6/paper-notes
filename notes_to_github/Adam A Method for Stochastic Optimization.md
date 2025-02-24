**Paper URL:** [arXiv](https://arxiv.org/abs/1412.6980)


## Abstract
Adam（Adaptive Moment Estimation）は、確率的勾配降下法（SGD）の最適化手法の一つであり、適応的な学習率調整を行うことで勾配ベースの最適化を効率化するアルゴリズムである。本論文では、Adamのアルゴリズムを導入し、勾配の1次および2次モーメントの移動平均を利用して適応的なステップサイズを決定する仕組みを説明する。


## Key Points
- Adamは勾配の1次モーメント（移動平均）と2次モーメント（分散）を活用し、適応的な学習率を決定する。
- モーメントのバイアス補正を行うことで、初期の不安定性を軽減し、収束を促進する。
- Adamの特性について：
    - 勾配のスケーリングに対して不変：勾配がスケールしても更新量は一定であり、最適なステップサイズが維持される。
    - 適応的なステップサイズの制限：ハイパラにより、学習率が適切な範囲内で調整される。
    - 非定常な目的関数への対応：損失関数が時間とともに変化しても安定して学習できる。
    - スパースな勾配に対応：適応的な更新により、勾配がまばらな場合でも効果的に学習が進む。
    - 自動的なステップサイズのアニーリング：収束に向けて、学習率が適切に減衰される。
- 実験により、ロジスティック回帰、多層パーセプトロン（MLP）、畳み込みニューラルネットワーク（CNN）での有効性を実証。
-     ![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/logistic_regression_trainging_negative_log_likelihood_on_mnist_and_imdb.png)
-     ![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/training_of_multilayer_nn_on_mnist_images.png)
-     ![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/convolutional_nn_traing_cost_and_traing_cost_for_the_first_three_epochs.png)


## Considerations
- 最近では、スパースなパラメータ更新がホット？
- ハイパラは自動調整が好ましい
- 局所最適解の耐性について
- 再現実験したい気持ち


## Related Work 
[- [[AlphaAdam Asynchronous Masked Optimization with Dynamic Alpha for Selective Updates]]](https://arxiv.org/abs/2501.18094)


## Labels
#Year-2015 #Optimization 