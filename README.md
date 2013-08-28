detectCharProject
=================

forParallelProcessing
#局所並列処理のための文字抽出アルゴリズム  
  
####情景画像から文字領域を抽出するアルゴリズム。

このアルゴリズムは、輝度値変換・ベース画像生成・ノイズ抽出・文字候補抽出・文字抽出の5過程からなる。  
入力はカラー画像、出力は二値画像である。


###輝度値変換過程
RGB値を輝度画像へ変換する。  
`gs.exec`

###ベース画像生成過程
輝度画像に対して平滑化後二値化する。  
`BaseImageCreation.exec`

###ノイズ抽出過程
輝度画像に対して文字消去を行った後に二値化する。  
`NoiseExtraction.exec`

###文字候補抽出過程
前述の二つの二値画像の差分を取り、文字領域をおおまかに抽出する。  
`CharacterCandidateDitection.exec`

###文字抽出過程
画素値を各領域の重心方向へ移動し合算することにより、領域の大きさを求める。  
その後、文字として適当な大きさの領域のみを出力する。  
`MoveToCenter.exec`  
`SizeJudge.exec`  
`NoiseElimination.exec`





