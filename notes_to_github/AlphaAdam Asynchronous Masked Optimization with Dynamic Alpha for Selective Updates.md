**Paper URL:** [arXiv](https://arxiv.org/abs/2501.18094)


## Abstract
AlphaAdamは、レイヤー内のパラメータ更新を非同期にマスクし、動的に更新強度を調整することで、収束を加速し、学習の安定性を向上させる。具体的には、過去のモメンタムと勾配の方向の一貫性に基づいてパラメータのマスクを構築し、適応的なマスク強度戦略を組み合わせることで、効率的な最適化と理論的収束保証を提供する。本手法は、ほとんどのモメンタムベースのオプティマイザに適用可能である。GPT-2の事前学習やRoBERTa・Llama-7Bのファインチューニングなどの広範な実験を通じて、AlphaAdamがAdamWなどの最先端手法を上回る収束速度と計算効率を達成することを示す。


## Key Points
- 非同期マスキング: 勾配と過去のモメンタムの方向の類似性を利用して、パラメータの更新を選択的にマスク
	- モメンタムは勾配の累積情報を表すため、過去のモメンタムを考慮する方が最適化が安定
- 動的α戦略: マスクされた更新の影響を補償し、学習の効率性と安定性を向上
- 理論的収束保証: TransformerのHessian特性を考慮し、AlphaAdamの収束性を証明
- 大規模LLMへの適用: GPT-2、RoBERTa、Llama-7Bに適用し、AdamWを超える性能を実証
- 計算コスト削減: メモリ効率と計算効率を向上させながら、収束速度を向上

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/AlphaAdam_Asynchronous_Masked_Optimization_with_Dynamic_Alpha_for_Selective_Updates_1.png)


## Considerations
- 非同期マスキングの影響
	- スパースなパラメータ更新が促進されている
- モメンタム＋学習率調整＋非同期マスク


## Related Work 
[- [[ADAM: A METHOD FOR STOCHASTIC OPTIMIZATION]]](https://arxiv.org/abs/1412.6980)



## Labels
#Year-2025 #Optimization 