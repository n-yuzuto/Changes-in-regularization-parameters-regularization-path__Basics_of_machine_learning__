# Changes-in-regularization-parameters-regularization-path-
Wineデータを訓練事例とテスト事例に分割し、 10^6から10^-3まで正則化パラメータを変化させつつ、訓練事例でridgeとLASSOを学習させました。  

プログラムの実行結果は、その正則化パラメータの変化(正則化パス)を表しています。

## 考察
正則化パラメータを大きくした時に、その特徴の予測に与える影響(係数の絶対値大きさ)が(多くの場合)減少している。  
  - L2正則化項、L1正則化項ともに、絶対値を大きいパラメータにペナルティ（罰則）を与えるため

正則化パラメータを大きくした時に、その特徴の予測に与える影響(係数の絶対値の大きさ)が増加することがある. 
 - L2正則化項、L1正則化項ともに、正則化パラメータを大きくすることによって、絶対のを大きいパラメータにペナルティ（罰則）が与えられ、全体の傾向としては絶対値が小さくなる。ただし、各パラメータの予測への影響度はそれぞれ異なるため、ある特徴量に対応するパラメータの影響度が減少、あるいはゼロになることによって、別のパラメータの影響度が相対的に高まり、結果として、正則化パラメータを大きくしても、そのパラメータの絶対値が大きくなることがある。

## まとめ
　リッジ回帰では正則化パラメータを大きくしていくと、どのパラメータもその複雑さ(パラメータの絶対値、原点からのユークリッド距離における遠さ)が同様に抑制され、値は徐々にゼロに近づくが、非常に正則パラメータを大きくしない限りゼロにはならない。一方、LASSOにおいて正則化パラメータを大きくしていくと、予測への影響が小さい特徴に対応するパラメータから順番に値がゼロに抑制される。この違いは、利用している正則化項の幾何的な形状によって発生している。ラッソが目的関数にもつL1正則化項の等高線の形状のため、目的関数の等高線と正則化項の等高線の接する部分が軸上になりやいが、リッジ回帰にはそのような性質はないことから、このような違いが発生する。

***
.ipynbファイルが開かれない時は、こちらのリンクにURLを貼ってご覧になってください。  
[nbviewer](https://nbviewer.jupyter.org/)
