**Paper URL:** [arXiv](https://arxiv.org/abs/2406.03768)
**Github URL:** https://github.com/chen123CtrlS/EnhancingICL_SVDPruning


## Abstract
本論文では、大規模言語モデル（LLM）における **in-context learning（ICL）** の性能向上を目的として、**SVDベースのウェイトプルーニング**の有効性を示す。特に、プルーニングがモデルの一般化性能に及ぼす影響を **暗黙的な勾配降下（GD）** の観点から理論的に解析し、一般化誤差の上限を情報理論的手法で評価した。 また、SVDによるプルーニングが、深い層と浅い層で異なる影響を及ぼすことを実験的に確認し、これを説明する数学的枠組みを構築した。最終的に、ICLの推論能力を向上させる **モデル圧縮と派生計算不要（Derivative-Free）なアルゴリズム** を提案し、ベンチマークデータセット上での有効性を検証した。


## Key Points
- SVDベースのウェイトプルーニングがICLの性能を向上させる
    - 深層のプルーニングは安定した性能向上をもたらすが、浅層のプルーニングは急激な性能低下を引き起こす。
- ICLはTransformerにおける暗黙的な勾配降下の一形態である
    - ICLの軌跡を勾配降下の軌跡として表現し、一般化誤差（母集団リスクと 経験リスク間の差）の上限を理論的に導出。
    - SVDベースのウェイトプルーニングが **ICLにおける勾配ノルムの制御** に寄与し、汎化性能の向上につながることを示す。
- ICLの下流タスクに適用可能な圧縮アルゴリズムを提案
    - 各層の条件数を考慮し、最適なプルーニング率を決定する手法（Algorithm 1）。
    - ベンチマークデータセット（SST-2, AGNEWS, EMOC, MRPC, RTE, CB, COPA）で有効性を検証。

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/Enhancing_In_Context_Learning_Performance_with_just_SVD_Based_Weight_Pruning_A_Theoretical_Perspective_1.png)


## Considerations
- ICLは暗黙的なGDによるメタ最適化なのか？
	- 通常のGDでは、ミニバッチ内のデータ順序は重要ではないが、ICLではデモの順序が重要になる。
	- 類似点は多いものの、GD単体では説明できなそう


## Related Work
[- [[Do pretrained Transformers Learn In-Context by Gradient Descent?]]](https://arxiv.org/abs/2310.08540)
[- [[In-context Learning on Function Classes Unveiled for Transformers]]](https://openreview.net/forum?id=rJkGOARXns&referrer=%5Bthe%20profile%20of%20Bo%20Jiang%5D(%2Fprofile%3Fid%3D~Bo_Jiang2))
[- [[Is In-Context Learning in Large Language Models Bayesian A Martingale Perspective]]](https://arxiv.org/abs/2406.00793)


## Labels
#Year-2024  #In-context-Learning #Model-Compression 
