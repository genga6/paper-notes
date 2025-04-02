**Paper URL:** [arXiv](https://arxiv.org/abs/2310.08540)
**Github URL:** 


## Abstract
本研究では、In-Context Learning（ICL）とGradient Descent（GD）が本当に同等なのかという問いを、理論的・実験的に検証した。既存のICL ≈ GD仮説は、ICL目的で訓練された特殊なTransformerや手作業で構築された重み行列に基づいているが、これは現実のLLMとは大きく異なる。著者らは、自然な事前学習を経たTransformer（LLaMA-7B）を用い、順序感度・出力分布・性能指標の観点からICLとGDを比較。結果として、両者は異なる動作原理を持ち、ICL ≈ GD という仮説は現時点では成立しない可能性が高いことを示した。


## Key Points
- **理論的前提と問題提起**
    - 既存の ICL ≈ GD 仮説は、**ICL目的で明示的に訓練されたTransformer** や、**手作業で構築された重み行列**を前提にしており、事前学習LLMとは乖離している。
    - 本研究は、自然な事前学習を経たTransformer（LLaMA-7B）を用いて、ICLとGDの等価性を実験的に検証する。
- **順序感度による検証**
    - **GDは順序安定（order-stable）**であり、入力順に依存しない。
    - 一方で**ICLは順序に非常に敏感**であり、同じデモでも並び順で出力が変わる。
    - したがって、ICLとGDが同等であるならば順序感度も一致するはずだが、実験結果はこの前提を否定している。
- **実験的検証（LLaMA-7Bを用いた比較）**
    - ICLとGDは出力分布が大きく異なる：**Token Overlap** や **Overlap Cosine Similarity** 指標において、両者の差が顕著。
    - **ICLは少数のデモでも高精度を示す**が、GDは過学習の傾向があり、多数のデモが必要。
    - ĜD（部分的パラメータ更新）による学習も、ICLと同様の動作は示さなかった。
- **理論モデルとの乖離**
    - 先行研究が示すGD的構造は、**スパースかつ理想化された重み行列**に依存しており、実モデル（LLaMAなど）では重みの分布が大きく異なる。
    - 実際のモデルでは、パラメータは訓練中に変化を続けており、**一意のGD実行重み**に収束することはない。
    - このことは、ICLが「特定の重みに依存したGDの模倣」ではなく、**より柔軟な学習表現**によって成立している可能性を示唆する。

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/Position_Do_pretrained_Transformers_Learn_In_Context_by_Gradient_Descent_1.png)

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/Position_Do_pretrained_Transformers_Learn_In_Context_by_Gradient_Descent_2.png)


## Considerations
- マーチンゲール性
	- GDは順序安定なアルゴリズムだが、現状のLLMはマーチンゲール性を満たさないという報告がある。本論文でも順序に敏感であることが示されており、ICLはGDのような挙動をしていないように見える。


## Related Work 
[- [[In-context Learning on Function Classes Unveiled for Transformers]]](https://openreview.net/forum?id=rJkGOARXns&referrer=%5Bthe%20profile%20of%20Bo%20Jiang%5D(%2Fprofile%3Fid%3D~Bo_Jiang2))
[- [[Is In-Context Learning in Large Language Models Bayesian A Martingale Perspective]]](https://arxiv.org/abs/2406.00793)


## Labels
#Year-2023  #In-context-Learning 
