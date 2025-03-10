**Paper URL:** [arXiv](https://arxiv.org/abs/2412.13243)
**Github URL:** 


## Abstract
本研究では、**Context Distillation（CD）** を提案し、ICLの情報をモデルパラメータに内在化することで、計算コストを削減しつつ汎化性能を向上させる。CDは、1.3BパラメータのOPTモデルから125Mモデルへ知識蒸留を行い、モデルサイズを2.5GBから0.25GBに削減しながらも、ICL単独と比較して50%近い精度向上を達成した。特に、CDはメモリ消費を最大60%削減し、従来のパターンベースのファインチューニングよりも20%高いOut-of-domain精度を示した。


## Key Points
- 実験設定
	- Multi-Genre Natural Language Inference（MNLI）データセットを使用。
	- 以下のモデルを比較: 
		- ベースライン（OPT125モデル）
		- ICL
		- PBFT: パラメータベースファインチューニング
		- CD: コンテキスト蒸留
- 実験結果
	- CDはICLと比べてOut-of-domain精度を50%向上し、特に低リソース環境でのタスク適応能力を示す。
	- CDはOut-of-domainにおいて、最も安定かつ高精度。
	- GPUメモリ使用量を最大60%削減しつつ、計算時間を短縮。
	- LoRAやBitFitを組み合わせることで、メモリ消費をさらに削減可能。

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/In_Context_Learning_Distillation_for_Efficient_Few_Shot_Fine_Tuning_1.png)

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/In_Context_Learning_Distillation_for_Efficient_Few_Shot_Fine_Tuning_2.png)

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/In_Context_Learning_Distillation_for_Efficient_Few_Shot_Fine_Tuning_3.png)


## Considerations
- ICL-Dの違い
	- ICL-D:（In-context Learning Distillation） 
		- 大規模モデルが推論時に示す**ICLの振る舞い**を模倣させ、小規模モデルもプロンプトからFew-shot学習できるように蒸留する。
		- In-context learning用の損失と言語モデリング用の損失を組み合わせる
	- CD:（Context Distillation） 
		- プロンプトを含む入力文脈を教師モデルで処理させ、その**ロジット分布**と生徒モデルのロジット分布の間のKLダイバージェンスを最小化する形で知識蒸留。
		- より特定の分野に特化する可能性が高そう
- アプリケーション
	- 数百MB程度のAIモデルであれば、ユーザーPC（ゲーミングPCレベル）でも推論できそう？
	- 量子化やプルーニングでより確実に運用できそうだが、ICL能力とトレードオフか。

## Related Work 
[- [[In-context Learning Distillation Transferring Few-shot Learning Ability of Pre-trained Language Models]]](https://arxiv.org/abs/2212.10670)

## Labels
#Year-2024  #In-context-Learning #Model-Compression 
