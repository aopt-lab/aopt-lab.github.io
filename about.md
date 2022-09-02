---
layout: default
title: 田邊研究室
---

### 研究室紹介

本研究室は人工知能・計算知能の一分野である進化計算の基礎研究を主に研究対象としています.
特に, ブラックボックス最適化, 多目的最適化, 進化アルゴリズムの振る舞いの実験的解析, 適応的パラメータ制御, 適応度地形解析, 自動アルゴリズム構成, 自動アルゴリズム選択, ベンチマーキング方法論の設計に現在関心があります.
学術研究の目的である知の体系化に貢献するために, 研究成果は積極的に英語論文として公開することを心がけています.
以下では, 本研究室 (2022年現在は田邊一人) の研究成果の一部を簡単に紹介します.


#### 適応度地形解析

対象問題がどのような性質を有するのかを明らかにできれば, その性質に適した最適化アルゴリズムを設計・選択することができます.
また, ある特定の最適化アルゴリズムがなぜうまく動作する, またはしないのかを知る手がかりとなります.
適応度地形解析 (fitness landscape analysis) では, 対象問題の探索空間の1つ以上の性質を定量化します.
ここでいう性質とは問題領域に依存しますが, 例えばブラックボックス最適化の場合は多峰性, 大域的多峰性, 変数分離不可能性, 悪スケール性などです.
進化計算コミュニティでは古くから適応度地形解析の研究がされています.

Exploratory landscape analysis (ELA) はブラックボックス最適化において最も有用な適応度地形解析手法の1つです.
ELAでは小さなサイズの解集合を元に, 人間には理解できない低レベルの数値的特徴量集合を生成します.
生成された特徴量集合は, 性質を分類する分類モデルの学習に使用されます.
例えば, 対象問題の多峰性は「ない」, 「弱い」, 「強い」などの3つに分類できます.
その他にも, 特徴量集合は自動アルゴリズム選択にも使用されます.
ELAは10次元程度の規模の問題 (設計変数が10個程度の問題) において有用性が報告されていますが, それ以上の次元には適用された事例がほとんどありません.
次の論文では, 高次元ブラックボックス最適化では計算コストが問題となりELAの一部特徴量の計算が困難であることを明らかにしました.
また, この問題を解決するために, 次元削減を使用してELAの計算コストを抑える枠組みを提案しました.

*  Ryoji Tanabe: **Towards Exploratory Landscape Analysis for Large-scale Optimization: A Dimensionality Reduction Framework**, Proc. ACM Genetic and Evolutionary Computation Conference [(GECCO2021)](https://gecco-2021.sigevo.org/HomePage), [pdf](https://arxiv.org/abs/2104.10301), [supplement](pdf/gecco21-supp.pdf), [code](https://github.com/ryojitanabe/ela_drframework), [feature data](https://drive.google.com/drive/folders/1MRiiirvi-bJmaO56h3xlZrGITR4oERIP), [slides](pdf/t-gecco2021-slides.pdf), [YouTube](https://www.youtube.com/watch?v=QlVjhVAJs6Y)

制御パラメータを自己適応的に調整する進化アルゴリズムが研究されていますが, そのパラメータ適応の振る舞いを理解するのは容易ではありません. 次の論文では「適応的パラメータ空間」という概念を提案し, 適応型差分進化手法の振る舞いを解析しました:

*  Ryoji Tanabe: **Analyzing Adaptive Parameter Landscapes in Parameter Adaptation Methods for Differential Evolution**, Proc. ACM Genetic and Evolutionary Computation Conference [(GECCO2020)](http://gecco-2020.sigevo.org/), [pdf](https://arxiv.org/abs/2009.12531), [supplemental-pdf](pdf/t-gecco2020-supp.pdf), [code](https://github.com/ryojitanabe/APL), [slide](pdf/t-gecco2020-slide.pdf)

#### ベンチマーキング

一般的に, 強い仮定をおかずに進化アルゴリズムの性能を理論的に評価することは困難です.
これは進化アルゴリズムが有する確率的, 反復的, 集団的などの要素のためです.
そのため, 多くの場合は進化アルゴリズムの性能は実験的に評価されます.
しかし, 様々な要素を加味する必要があるため, 意味がありかつ信頼できる実験結果を得るのもまた困難です.
ベンチマーキングの研究分野では, 既存の実験方法の問題点を明らかにし, より良い実験方法を考えます.

次の論文では, 特徴量に基づくオフライン型自動アルゴリズム選択システムの既存のベンチマーキング方法の問題点を指摘するとともに, 改善案を提示しています.

* Ryoji Tanabe: **Benchmarking Feature-based Algorithm Selection Systems for Black-box Numerical Optimization**, [IEEE Transactions on Evolutionary Computation](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=4235), 2022. [pdf](https://arxiv.org/abs/2109.08377), [link](https://ieeexplore.ieee.org/document/9762332), [code](https://github.com/ryojitanabe/as_bbo)

次の論文では, 適応型進化アルゴリズム (差分進化) において, 適応機能の性能のみを評価する方法を提案しています:

* Ryoji Tanabe and Alex Fukunaga: **Reviewing and Benchmarking Parameter Control Methods in Differential Evolution**, [IEEE Transactions on Cybernetics](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=6221036), 2020. [link](https://ieeexplore.ieee.org/document/8626758), [pdf](https://arxiv.org/abs/2010.01035), [supplemental-pdf](pdf/tf-tcyb2018-supp.pdf)
*  Ryoji Tanabe and Alex Fukunaga: **TPAM: A Simulation-Based Model for Quantitatively Analyzing Parameter Adaptation Methods**, Proc. ACM Genetic and Evolutionary Computation Conference [(GECCO2017)](http://gecco-2017.sigevo.org/), [(pdf)](https://arxiv.org/abs/2010.01877), [(supplemental-pdf)](pdf/tf-gecco2017-supp.pdf), [(slide)](pdf/tf-gecco2017-slide.pdf)

次の論文では, state-of-the-artな進化型多目的最適化アルゴリズムの性能が無限アーカイブを使用することでどのように変化するのかを解析しています:

* Ryoji Tanabe, Hisao Ishibuchi, and Akira Oyama: **Benchmarking Multi- and Many-objective Evolutionary Algorithms under Two Optimization Scenarios**, IEEE Access [(link-to-pdf)](http://ieeexplore.ieee.org/document/8031325/), [(supplemental-website)](https://sites.google.com/site/benchmarkingmoeas/)

#### 自動アルゴリズム選択

ブラックボックス最適化の問題領域に対象を絞っても, これまでに数多くの最適化アルゴリズムが提案されています.
しかし, 一般的に最良な最適化アルゴリズムは問題依存です.
そのため, ユーザは自身の対象問題に対して最も適しているであろう1つの最適化アルゴリズムを試行錯誤を通して選ばなければなりません.
このアルゴリズム選択問題は, 最適化アルゴリズムの実応用の妨げとなります.
自動アルゴリズム選択は, 名前の通り適した最適化アルゴリズムを自動で選択する研究テーマです.
自動アルゴリズム選択はアルゴリズム選択問題の有効な解決策です.
一般的に自動アルゴリズム選択では, 機械学習により最適化アルゴリズムの性能を予測する回帰モデル, またはアルゴリズムの良し悪しを予想する分類モデルを構築します.

次の論文では, ブラックボックス最適化の特徴量に基づくオフラインアルゴリズム選択システムを実験的に解析しています:

* Ryoji Tanabe: **Benchmarking Feature-based Algorithm Selection Systems for Black-box Numerical Optimization**, [IEEE Transactions on Evolutionary Computation](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=4235), 2022. [pdf](https://arxiv.org/abs/2109.08377), [link](https://ieeexplore.ieee.org/document/9762332), [code](https://github.com/ryojitanabe/as_bbo)

#### 自動アルゴリズム構成

#### 進化型多目的最適化




