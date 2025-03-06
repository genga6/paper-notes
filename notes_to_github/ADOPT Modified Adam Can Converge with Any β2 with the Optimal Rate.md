**Paper URL:** [arXiv](https://arxiv.org/abs/2411.02853)
**Github URL:** https://github.com/iShohei220/adopt


## Abstract
Adamはディープラーニングで広く用いられる最適化手法だが、ハイパーパラメータの設定に依存して収束しない問題が指摘されている。本論文では、新しい適応勾配法**ADOPT**を提案し、どの$β_2$でも最適な収束率を達成できることを理論的に証明する。ADOPTは、勾配の現在値を2 次モーメント推定から除外し、モーメンタム更新と正規化の順序を変更することでAdamの非収束問題を解決する。また、多様なタスク（画像分類、自然言語処理、強化学習など）においてADOPTの優位性を実験的に検証した。


## Key Points
- Adamとの違い
	- ADOPTは現在の勾配 $g_t$ から2次モーメント $v_2$ を除外することでAdamの非収束問題を解決する。
	- モーメンタム更新と正規化の順序を変更することで、収束率 $O(1/sqrt(T))$ を保証する。
- トイプロブレムを用いた実験
	- Adam: パラメータ$β_2$の値に依存して誤った解に収束する。また、ノイズが大きくなると、どの$β_2$でも収束しないケースが発生する。
	- AMSGrad: 勾配のノイズが大きい場合、収束が極端に遅くなる。
	- ADOPT: 非収束問題を解決できている。
- ADOPTの適用範囲
	- 画像分類（CIFAR-10, ImageNet）、生成モデル（NVAE）、言語モデル（GPT-2, LLaMA-7B）など幅広いタスクでAdamやAMSGradより高い性能を発揮。


![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/ADOPT_Modified_Adam_Can_Converge_with_Any_β2_with_the_Optimal_Rate_1.png)

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/ADOPT_Modified_Adam_Can_Converge_with_Any_β2_with_the_Optimal_Rate_2.png)


## Considerations
- Adamと計算コストがほぼ同じなので、ADOPTをベースラインに据えることができそう
- transformersで使われる最適化手法（AdamWとかLion？）との性能比較はどうか
- 近年一部のパラメータをマスク化する手法があるが、ADOPTバージョンではどうか。
 
## Related Work 
[- [[Adam A Method for Stochastic Optimization]]](https://arxiv.org/abs/1412.6980)
[- [[AlphaAdam Asynchronous Masked Optimization with Dynamic Alpha for Selective Updates]]](https://arxiv.org/abs/2501.18094)


## Labels
#Year-2024  #Optimization 
