**Paper URL:** [arXiv](https://arxiv.org/abs/2501.11599)


## Abstract
Chain-of-Thought（CoT）は一部のケースで推論能力を向上させるが、論理的な誤りを含むことがある。本研究では、**Syllogistic-Reasoning Framework of Thought（SR-FoT）** を提案し、LLMが三段論法に基づいた演繹推論を実行できるようにする。この手法では、問題の解釈、主要前提の提案、補助前提の生成・適用という段階的な推論フレームワークを採用し、最終的に厳密な推論を可能にする。ScienceQA、StrategyQA、BoolQなどの知識ベース推論タスクに対する評価実験において、SR-FoTはCoTを含む既存手法を上回る精度を達成した。


## Key Points
- LLMの演繹推論の課題
    - CoTは推論能力を向上させるが、厳密な演繹推論には不十分。
    - LLMは知識ベースの推論タスクにおいて、正しい前提に基づく演繹推論ができない場合がある。
- SR-FoTの導入
    - **三段論法（Syllogistic Reasoning）** に基づく新しい推論フレームワーク。
    - 問題の解釈 → 大前提の生成 → 小前提の生成 → 最終推論 の4段階構造を持つ。
- 知識ベース推論タスクでの評価
    - ScienceQA、StrategyQA、BoolQの3つのデータセットを用いてSR-FoTの評価を実施。
    - GPT-3.5-turbo、DeepSeek-V2、Qwen1.5-32B-Chatの3つのLLMで実験を行い、SR-FoTは一貫して高い精度を示した。
    ![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/comparison_with_the_state_of_the_art_methods.png)


- 推論精度向上のメカニズム
    - SR-FoTは問題ごとに適切な前提を導き出し、それを基に厳密な演繹推論を実行。
    - ただし問題によって前提の選択が曖昧になり、誤った結論に達するリスクがある。


## Considerations
- アプリケーション
	- 論理的なタスク（法的判断、証明など？）に応用できる？
	- 初手はCoT、より厳密さが必要であればSR-FoTというアプローチ
- ICLに論理的な手順を落とし込む役割


## Related Work 
- 

## Labels
#Year-2025 #Prompt-Engineering 
