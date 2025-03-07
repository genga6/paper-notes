**Paper URL:** [arXiv](https://arxiv.org/abs/2212.10670)
**Github URL:** 


## Abstract
本研究では、**in-context learning distillation（ICL-D）** を提案し、大規模モデルのFew-shot学習能力を小規模モデルへ蒸留する手法を開発した。具体的には、ICLの目標と従来の言語モデリングの目標を組み合わせることで、より効果的な知識転送を実現する。また、**Meta In-context Tuning（Meta-ICT）** と **Multitask In-context Tuning（Multitask-ICT）** の 2つのFew-shot学習パラダイムを比較し、それぞれの特性を分析した。

実験の結果、ICL-D は LAMA および CrossFit ベンチマークにおいて一貫した性能向上を示し、Multitask-ICT の場合、モデルサイズを 93% 削減しても 91.4% の性能を維持できることが確認された。


## Key Points
- ICL-D による学習能力の転移
    - LLMの few-shot 学習能力を生徒モデルへ蒸留する手法を提案
    - 言語モデルの目標と in-context learning の目標を組み合わせることで学習効果を強化
- 二つの few-shot 学習パラダイム
    - **Meta-ICT**: メタ学習により unseen タスクに適応（計算コストは低いが、性能は限定的）
    - **Multitask-ICT**: 各タスクごとに微調整を行い、適応能力を向上（高性能だが計算コストが増加）
- 性能比較
    - Multitask-ICT は Meta-ICT よりも精度が高い
    - ICL-D により、教師モデルと比較して生徒モデルの性能が 91.4% まで維持可能
    - LAMA では、ICL-D + 言語モデルの distillation（ICL-D(LM)）が特に効果的
- 知識蒸留の最適化
    - 言語モデルの目標を組み合わせた蒸留は、Multitask-ICT では有効だが、Meta-ICT ではむしろ一般化性能を下げる
    - 生徒モデルは教師モデルのスケールアップに必ずしも比例して学習効果が向上するわけではない
    - 学習データの増加よりも、タスクの多様性の方が性能向上に寄与する

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/In_context_Learning_Distillation_Transferring_Few_shot_Learning_Ability_of_Pre_trained_Language_Models_1.png)

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/In_context_Learning_Distillation_Transferring_Few_shot_Learning_Ability_of_Pre_trained_Language_Models_2.png)

![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/In_context_Learning_Distillation_Transferring_Few_shot_Learning_Ability_of_Pre_trained_Language_Models_3.png)


## Considerations
- ICLとモデル圧縮
	- ICLはリアルタイム性と相性がよさそう
	- Transformerは言語以外にも応用されており、マルチモーダルな文脈から適応できると面白い
	- プルーニングや量子化と組み合わせる


## Related Work 



## Labels
#Year-2022 #In-context-Learning #Model-Compression
