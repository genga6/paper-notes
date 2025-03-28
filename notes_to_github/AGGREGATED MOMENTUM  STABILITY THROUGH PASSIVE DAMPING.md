**Paper URL:** [arXiv](https://arxiv.org/abs/1804.00325)
**Github URL:** 


## Abstract
本研究では、**Aggregated Momentum（AggMo）** を提案し、複数の減衰係数 β を持つモメンタムベクトルを平均化することで、振動を抑えつつ高速な収束を実現する最適化手法を開発した。従来のモメンタム法は β の選択により収束速度と安定性のトレードオフがあったが、AggMo はこの問題を解消する。さらに、Nesterov モメンタムが AggMo の特殊ケースであることを示し、二次関数上の収束解析とオンライン凸最適化における理論保証も行った。

実験の結果、AggMo は古典的モメンタムや Nesterov モメンタムよりも高速で安定した収束を実現し、Autoencoder、CNN、ResNet、LSTM など多様なアーキテクチャで優れた性能を示した。


## Key Points
- 振動を抑えた高速最適化手法「AggMo」の提案
    - 複数の異なる β を使ったモメンタムベクトルを用意し、それらを平均してパラメータを更新
    - 物理学の「受動的減衰（Passive Damping）」から着想を得たアプローチ
- モメンタム法の一般化と理論的解析
    - Nesterov モメンタムは AggMo の特殊ケースであることを数式的に再構成
    - 二次関数とオンライン凸最適化において AggMo の収束性を理論的に保証（Regret は O(√T) に収束）
- 実験による性能検証
    - MNISTでのAutoencoder学習ではAggMoが最速かつ最高精度
    - CIFAR-10/100 の画像分類では、Nesterov や Adam よりも高速収束を実現
    - Penn Treebank によるLSTM言語モデルでは、Adamと同等の性能を達成
- ハイパーパラメータ調整の不要性と安定性
    - デフォルト設定（β = [0, 0.9, 0.99]）でほとんどのタスクにおいて高い性能
    - 大きな β（例: 0.999）でも振動せず安定して学習が進む（既存研究との差別化）

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/comparison_with_the_state_of_the_art_methods.png)


## Considerations
- 個別のベクトルごとに学習率やスケジューリングの調整をせず、単純な平均化でも高速な収束を実現できる点が興味深い。


## Related Work 
[- [[Adam A Method for Stochastic Optimization]]](https://arxiv.org/abs/1412.6980)
[- [[ADOPT Modified Adam Can Converge with Any beta2 with the Optimal Rate]]](https://arxiv.org/abs/2411.02853)
[- [[AlphaAdam Asynchronous Masked Optimization with Dynamic Alpha for Selective Updates]]](https://arxiv.org/abs/2501.18094)


## Labels
#Year-Before-2020 #Optimization 