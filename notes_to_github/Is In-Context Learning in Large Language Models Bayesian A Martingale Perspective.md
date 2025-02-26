**Paper URL:** [arXiv](https://arxiv.org/abs/2406.00793)
**Github URL**: https://github.com/meta-inf/bayes_icl


## Abstract
本研究は、大規模言語モデル（LLM）の **in-context learning（ICL）** がベイズ推論的かどうかをマーチンゲール性の観点から分析した。ベイズ推論ならば満たすべき「マーチンゲール性」を実験的に検証した結果、多くの最新LLMがこの性質を満たさず、ICLは厳密なベイズ推論ではないことを示した。また、データ量の増加に伴う不確実性の減少が、ベイズ推論の理論的予測と一致しないことも確認した。


## Key Points
- マルチンゲール性と交換可能性
    - データの挿入順序や欠損データの補完に依存しない予測にはマーチンゲール性が必要だが、現状のLLMはそれを満たさないことを実験で確認。
    - LLMは自身が生成した欠損データ（プロンプト内のデータ）により予測が変動する**Introspective hallucinations（内省的幻覚）** を起こす可能性がある。
 
![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/Is_In_Context_Learning_in_Large_Language_Models_Bayesian_A_Martingale_Perspective_1.png)

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/Is_In_Context_Learning_in_Large_Language_Models_Bayesian_A_Martingale_Perspective_2.png)

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/Is_In_Context_Learning_in_Large_Language_Models_Bayesian_A_Martingale_Perspective_3.png)

- 不確実性の分解
    - LLMが持つ不確実性を「データを増やすことで減少する**認識的不確実性（Epistemic Uncertainty）**」と「データが無限でも残る**偶然的不確実性（Aleatoric Uncertainty）**」に分ける方法を理論的に提示。
    - 実験により、LLMの認識的不確実性の減少速度がベイズモデルと一致しないことを確認。

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/Is_In_Context_Learning_in_Large_Language_Models_Bayesian_A_Martingale_Perspective_4.png)


## Considerations
- Transformerの内部的な処理がベイズ推論とは異なるため、自分自身のデータでハルシネーションが生じる可能性はある。
	- Transformerが内部で「模倣的に勾配降下」していると仮定すればintrospective hallucinations現象は矛盾はしなさそう


## Related Work 
[- [[A Survey on In-context Learning]]](https://arxiv.org/abs/2301.00234)
[- [[In-context Learning on Function Classes Unveiled for Transformers]]](https://openreview.net/forum?id=rJkGOARXns&referrer=%5Bthe%20profile%20of%20Bo%20Jiang%5D(%2Fprofile%3Fid%3D~Bo_Jiang2))


## Labels
#Year-2024  #In-context-Learning 
