**Paper URL:** [arXiv](https://arxiv.org/abs/2411.05285)
**Github URL:** 


## Abstract
LLMエージェントは自律性と不確定な振る舞いを持ち、継続的に進化するため、AIの安全性に関する重大な懸念を引き起こす。DevOpsの視点から、**エージェントの可観測性（Observability）** を実現することは、AIエージェントの内部動作を把握し、異常を検出し、潜在的な障害を予防することを可能にする。

本論文では、**AgentOps** という概念を提唱し、エージェントのライフサイクル全体を通じてトレースすべき生成物と関連データを特定する包括的な分類法を開発した。この分類法は、既存のAgentOpsツールの体系的なマッピング研究に基づき、エージェントの監視、ロギング、分析をサポートするインフラ設計の参照テンプレートとして機能する。


## Key Points
- エンティティ・リレーションシップモデルの提案
	- 目標、計画、タスク、ツール、LLM、評価、ガードレールの関係を整理。 
	- これにより、エージェントの意思決定過程をトレースし、異常検出やガードレール設定を強化。
- AgentOpsのツールマッピング研究
	- 17の主要なAgentOpsツールを特定し、それらの機能を比較・分類。
	    - 代表的なツール例：**AgentOps, Langfuse, Arize, Datadog, Portkey など**。
	- 各ツールを以下の観点で比較：
	    - カスタマイズ性
	    - プロンプト管理
	    - 評価
	    - フィードバック収集
	    - モニタリング
	    - トレーシング
	    - ガードレール
	- 監視機能の違いを分析：
	    - LLMレベルの監視に特化（例：Langfuse, Arize）。
	    - エージェントレベルのトレーシングが可能なツールは少数（例：AgentOps, Datadog）。
	    - ガードレール機能を備えるツールは限られる。 

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/AGENTOPS_ENABLING_OBSERVABILITY_OF_LLM_AGENTS_1.png)


## Considerations
- 提案されたERMの概念は有望だが、具体的な適用例や実証実験がない。
	- LLMの不確実性（出力の一貫性、ハルシネーション、コンテキストドリフトなど）をこのモデルでどの程度トレースできるかが明らかになっていない。
	- とはいえ、説明可能性やガードレール機能の追加は魅力的
- エージェントの挙動をリアルタイムかつ詳細にトレースすると計算コストが高くつきそうではある。


## Related Work 


## Labels
#Year-2024  #Multi-Agent 
