**Paper URL:** [arXiv](https://arxiv.org/abs/2310.01783)
**Github URL**: https://github.com/Weixin-Liang/LLM-scientific-feedback


## Abstract
本論文では、大規模言語モデル（LLM）が研究論文に対して有益なフィードバックを提供できるかを検証するために、GPT-4を用いた自動フィードバック生成パイプラインを開発・評価した。Nature系ジャーナル（3,096本）およびICLR（1,709本）の論文に対するGPT-4のフィードバックを、人間のピアレビューと比較した結果、LLMのフィードバックと人間のレビューの重複度は、Nature系で30.85%、ICLRで39.23%であり、人間同士の重複（Nature系28.58%、ICLR35.25%）と同程度であった。また、ICLRの不採択論文では、GPT-4と人間のレビューの重複度がより高い（43.80%）。さらに、308名の研究者を対象としたユーザースタディにおいて、57.4%がLLMのフィードバックを「有益」と評価し、82.4%が「少なくとも一部の人間のレビューよりも有益」と回答した。一方で、GPT-4のフィードバックは「実験データの拡充」を求める傾向があり、モデル設計の詳細に関する深い批判が苦手であることが明らかになった。総じて、LLMは人間のレビューを補完し、特に迅速なフィードバックが求められる場面で有用であると考えられる。


## Key Points
- LLMによるフィードバックの精度評価
    - GPT-4のフィードバックは、人間のレビュアー同士のレビューと同程度の重複度を示す（Nature系30.85%、ICLR39.23%）。
	- 特に不採択論文ではGPT-4と人間のレビューの一致率が高く（43.80%）、**問題点の特定には有用**である可能性が高い。
- フィードバックの特性
	- LLMのフィードバックは 「データセットを増やすべき」「実験の追加を推奨する」など、特定の観点に偏る傾向がある。
	- 人間のレビュアーに比べ、新規性や技術的な詳細（特にモデル設計やアルゴリズム選択）に関する指摘が少ない。
	-  ただし、完全に一般的すぎるフィードバックではなく、ある程度論文ごとに個別の指摘を提供している。
- ユーザースタディの結果
    - 研究者の57.4%が「有益」、82.4%が「一部の人間のレビューよりも有益」と評価。
    - 65.3%の研究者が「LLMは人間のレビュアーが見落とした視点を提供できる」と回答。
- LLMの限界
	- 図表の解釈が不十分であり、論文内のグラフや数式の正確な理解には課題がある。

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/Can_large_language_models_provide_useful_feedback_on_research_papers_A_large_scale_empirical_analysis_1.png)

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/Can_large_language_models_provide_useful_feedback_on_research_papers_A_large_scale_empirical_analysis_2.png)


## Considerations
- フィードバックの質と具体性
	- プロンプトに「具体的に改善方法」を盛り込むように指示すればFBの質を向上できるか？
		- 「3つの具体的な改善方法」
		- 「新規性を評価し、類似論文と比較」
		- 「アブレーション実験の提案を必ず含める」など？
- LLMの限界
	- マルチモーダルLLMの活用で、図表を解析
	- 数学的な証明ツール（Leanとか？）との連携


## Related Work 
[- [[The AI Scientist Towards Fully Automated Open-Ended Scientific Discovery]]](https://arxiv.org/abs/2408.06292)
[- [[DOLPHIN Closed-loop Open-ended Auto-research through Thinking, Practice, and Feedback]]](https://arxiv.org/abs/2501.03916)

## Labels
#Year-2023 #Auto-Research 
