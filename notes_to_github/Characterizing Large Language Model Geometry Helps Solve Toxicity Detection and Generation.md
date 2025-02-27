**Paper URL:** [arXiv](https://arxiv.org/abs/2312.01648)
**Github URL**: https://github.com/RandallBalestriero/SplineLLM


## Abstract
本論文では、大規模言語モデル（LLM）の幾何学的特性を解析し、その結果を用いて毒性検出やRLHFの回避メカニズムを明らかにする。特に、マルチヘッドアテンション（MHA）の埋め込み空間とフィードフォワード層（MLP）のアフィン変換領域を解析し、プロンプトの設計がモデルの表現力や制約回避に与える影響を実証する。結果として、プロンプトを工夫することでRLHFの影響を回避し、通常は抑制される出力を生成できることが示された。


## Key Points
- MHAの幾何学的解析
    - MHAの出力は、入力トークンの凸包（convex hull）のミンコフスキー和として表現できる（Theorem 3.2）
    - これにより、LLMの埋め込み空間の内在次元を制御できる
- 毒性検出への応用
    - 幾何学的特徴（MHA出力の内在次元、MLP層のアフィン領域など）を用いることで、毒性を判別可能
    - Llama2-7BおよびMistral-7Bにおいて、既存の毒性検出手法を上回るROC-AUCを達成（99.18%）

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/Characterizing_Large_Language_Model_Geometry_Helps_Solve_Toxicity_Detection_and_Generation_1.png)

- RLHFの回避
    - 特定のプロンプト操作を行うことで、LLMの埋め込み内在次元を意図的に増加させ、RLHFによる抑制を回避可能
    - これは、モデルが特定の埋め込みサブスペースに制限されていることに起因する

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/Characterizing_Large_Language_Model_Geometry_Helps_Solve_Toxicity_Detection_and_Generation_2.png)

- MLP層の分割構造
    - MLP層は、連続的なアフィン変換（スプライン関数）によって構成されており、その分割数がLLMの表現力を決定する
    - MHAの内在次元が増加すると、MLPの非線形性が指数的に向上し、複雑なタスクの処理が可能になる


## Considerations
- RLHFの限界
	- 特定のプロンプト設計により、埋め込みの内在次元を増やし、RLHFの制約が適用されない領域へ誘導できてしまう
	- 毒性を持つ「特定の埋め込み次元」を特徴付けられたら良いが...
	- 制約を強化するには、埋め込み次元やMLPの分割構造を監視・制御する動的手法が必要？


## Related Work 


## Labels
#Year-2024  #Transformer 
