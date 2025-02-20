**Title:** In-context Learning on Function Classes Unveiled for Transformers  
**Tags:** In-context-Learning  
**Year:** 2024  
**Author:** Zhijie Wang, Bo Jiang, Shuai Li  
**Paper URL:** [OpenReview](https://openreview.net/forum?id=rJkGOARXns&referrer=%5Bthe%20profile%20of%20Bo%20Jiang%5D(%2Fprofile%3Fid%3D~Bo_Jiang2))


## Abstract 
Transformerベースのモデルが **in-context learning（ICL）** を通じて、何故多様な関数クラスを学習できるのかを解明する. 著者らは、Transformerがニューラルネットワークのパラメータに対して近似的な勾配降下（gradient descent）を実行できることを示し、必要なアテンションヘッド数、隠れ層の次元数、層の数の上限を導出した. また、線形関数、単位球の指示関数、スムーズな関数をTransformerが学習可能であることを証明し、線形回帰と分類の2つのタスクに対して同時に精度の高い予測が可能であることが示された. 

## Considerations
- **Transformerによる近似勾配降下**
	- Transformerがニューラルネットワークのパラメータに対して、**明示的な更新なしで** 近似的な勾配降下を実行（エミュレート？）できる点は非常に興味深い. 
	- ICLの解釈にはベイズ推論的な視点もあるが、「Transformerが暗黙的にGDを実行している」** という立場がやや優勢？ 
	- 言語モデルが内部に持つ膨大なパターンに、GDが含まれていることに起因？
	
- **関数クラスの学習能力**
    - Transformerは、**線形関数**、**分類タスク**、および **スムーズな関数** をICLで学習できる. 
    - 2層ニューラルネットワークでは不十分であり、より深いニューラルネットワークを利用した方がよい. 
    - Transformerの冗長性が寄与していると考えられるが、一方で量子化やプルーニングなどのモデル圧縮との関係はどうか？
    -
- **アルゴリズム選択能力**
	- Transformer は、線形回帰と分類という異なるタスクを ICL を通じて適切に識別し、最適な推論を行う能力を持つ。
	- これは、「Transformer が単なる関数近似器ではなく、タスクごとの最適なアルゴリズムを自動的に選択する仕組みを内部に持つ」可能性を示している。
	- ICL の本質は、適切なアルゴリズムを選択するプロセス？

## Related Work 
[- [[A Survey on In-context Learning]]](https://arxiv.org/abs/2301.00234)
