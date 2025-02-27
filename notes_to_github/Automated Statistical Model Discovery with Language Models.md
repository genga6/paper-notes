**Paper URL:** [arXiv](https://arxiv.org/abs/2402.17879)


## Abstract
統計的モデル探索は、膨大なモデル空間を探索するプロセスであり、特定の制約のもとで実行される。効率的な探索には、モデリングおよびドメイン知識の専門性が必要である。本論文では、大規模言語モデル（LM）のドメイン知識とプログラミング能力を活用し、自動統計モデル発見の手法「BoxLM」を提案する。本手法は「Boxのループ」のフレームワークに基づき、LMが確率的プログラムとして統計モデルを提案・批評・改良するプロセスを繰り返す。

BoxLMの有効性は、以下の3つの確率的モデリングの設定で評価される：

1. 限定されたモデル空間内での探索
2. オープンエンドなモデル空間上での探索
3. 自然言語の制約のもとでのモデル改良（例：「このモデルは生態学者にとって解釈可能でなければならない」）

実験結果より、BoxLMは人間の専門家が設計したモデルと同等の性能を持つモデルを特定できることが示された。また、古典的なモデルを解釈可能な形で拡張できる点が特徴である。本研究は、LM駆動のモデル探索の可能性を示唆している。


## Key Points
- BoxLMは、確率的プログラム（PyMC）を用いて、LLMが統計モデルを提案・批評・改良する新しい手法を示した。
- ドメイン固有言語（DSL）なしでモデル探索が可能であり、自然言語の制約（例：「解釈可能なモデル」）を反映できる。
	- ドメイン固有の制約...解釈可能性、境界条件、データの特性など
- Gaussian Processのカーネル探索では、Automatic Statisticianと同等の精度を達成。
- Lotka-Volterraモデルの改良では、ニューラルODE（常微分方程式）よりも優れたモデルを発見できた。
- メタデータなしの状態では、よりデータに適合する柔軟なモデルが選択されるが、それが必ずしもドメイン知識に基づいた最適なモデルとは限らない。
	- **柔軟性と解釈可能性のトレードオフが存在**


## Considerations
- データサイエンス
	- 自然言語による制約は、ビジネスでの応用が期待できそう
- LLMのモデリング
    - LLMがドメイン知識を有すると同時に、データの統計的特徴からICLしている？
    - メタデータあり: LLMはドメイン知識を反映し、専門家が考える「正しい」モデルを提案しやすい
	- メタデータなし: LLMはデータの統計的パターンをICLの形で学習し、よりデータ駆動的なモデルを提案する


## Related Work 



## Labels
#Year-2024 #Auto-Research #DataScience