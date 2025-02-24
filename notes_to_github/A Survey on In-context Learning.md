**Paper URL:** [arXiv](https://arxiv.org/abs/2301.00234)


## Abstract
本論文はICLの進展と課題を包括的に調査し、ICLの定義や関連研究との関係を整理する。  
ICLの学習能力を向上させるトレーニング戦略やプロンプト設計手法について議論し、データエンジニアリングや知識更新などの応用事例を紹介する。また、ICLの課題と今後の研究方向について提言を行い、そのメカニズムの解明と改善を促進することを目的とする。


## Key Points
- ICLの定義と特性
    - ICLは事前学習済みの言語モデルが少数の例をコンテキストとして学習し、**明示的なパラメータ更新なし**に推論を行う。
- ICLのトレーニング手法
    - Pretraining: ICL能力を向上させるための事前学習
    - Warmup: ICL推論前に追加の調整を行い、入力ラベルマッピングを学習
- プロンプト設計戦略
    - デモンストレーション選択: 最近傍検索（KATE）、情報理論に基づく選択（MI）、教師あり学習（EPR）。
    - デモンストレーションの順序付け: 局所エントロピー（GlobalE & LocalE）を用いた適切な並び替え。
    - 命令形式: 自動プロンプト生成（Self-Instruct, APE）、中間推論プロセスの活用。
- ICLの分析とメカニズム
    - 学習メカニズム:
        - **誘導ヘッド（induction heads）**が事前学習で得たパターンをもとにICL能力を発現。
        - Transformerの注意機構が暗黙的に**ベイズ推論**や**勾配降下**を模倣している可能性。
    - 影響因子:
        - 事前学習データの多様性がICLの性能を決定。
        - プロンプトのフォーマットやデモンストレーションの選択がICLの精度に影響。
![Image](https://raw.githubusercontent.com/genga6/paper-notes/main/images/A_Survey_on_In_context_Learning_1.png)

## Considerations
- 適切なデモンストレーションがICLの性能を最大化出来る点は、人間に似ていて興味深い。
- パラメータが局所解か、平坦解かによってICLにどのように影響するか（ICLのロバスト性？）


## Related Work 
[- [[In-context Learning on Function Classes Unveiled for Transformers]]](https://openreview.net/forum?id=rJkGOARXns&referrer=%5Bthe%20profile%20of%20Bo%20Jiang%5D(%2Fprofile%3Fid%3D~Bo_Jiang2))


## Labels
#Year-2022  #In-context-Learning 
