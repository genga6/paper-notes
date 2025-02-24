**Paper URL:** [OpenReview](https://openreview.net/forum?id=rJkGOARXns&referrer=%5Bthe%20profile%20of%20Bo%20Jiang%5D(%2Fprofile%3Fid%3D~Bo_Jiang2))


## Abstract
Transformerベースのモデルが **in-context learning（ICL）** を通じて、何故多様な関数クラスを学習できるのかを解明する。著者らは、Transformerが近似的な勾配降下を実行できることを示し、必要なアテンションヘッド数、隠れ層の次元数、層の数の上限を導出した。
また、線形関数、単位球の指示関数、スムーズな関数をTransformerが学習できることを証明し、線形回帰と分類タスクに対して精度の高い予測が可能であることが示した。


## Key Points
- 活性化関数 $r$ と損失関数 $l$ は有限の Barron ノルムを持つ（Assumption 3.1）
- 重み空間 $W$ はコンパクトであり、MLP の特定のパラメータ設定により $w$ を $W$ に射影できる（Assumption 3.2）
- ICL は Transformer の暗黙的な勾配降下（GD）をエミュレートしている可能性がある
- Transformer は線形関数・分類タスク・スムーズな関数を学習可能
- 層の深さとアテンションヘッド数が、ICL の性能を決定する重要な要素となる（2層NNでは不十分）
- Transformer は異なるタスクを ICL を通じて適切に識別できる


## Considerations
- Transformerによる近似勾配降下
	- ICL の解釈にはベイズ推論の視点もあるが、「Transformerが暗黙的にGDを実行している」という立場が優勢か？
	- 言語モデルが内部に持つ膨大なパターンに、GD のプロセスが暗に組み込まれている可能性
- 関数クラスの学習能力
    - 非スムーズな関数や複雑なタスクへの適用は？
    - Transformer の冗長性が学習に寄与している可能性があるが、一方で量子化やプルーニングなどの圧縮技術とのトレードオフは？
- アルゴリズム選択能力
	- ICL は単なる関数近似なのか、それともアルゴリズム選択のプロセスなのか？
	- タスクごとの最適なアルゴリズムを自動的に選択する仕組みを内部に持っている？


## Related Work 
[- [[A Survey on In-context Learning]]](https://arxiv.org/abs/2301.00234)


#Year-2024 #In-context-Learning
