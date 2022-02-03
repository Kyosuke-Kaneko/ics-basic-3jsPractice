# カメラ
Three.jsにはCamera3Dクラスがあることを、入門編で紹介しました。このCamera3Dがどのようにして利用できるのか、もう少し掘り下げて学んでみましょう。

Three.jsにさまざまな種類のカメラが搭載されています。

カメラの種類

 - THREE.PerspectiveCamera : 遠近感が適用されるカメラ
 - THREE.OrthographicCamera : 平行投影が適用されるカメラ

本節ではPerspectiveCameraとOrthographicCameraの2種類を掘り下げて解説します。

## PerspectiveCamera
遠近感を表現できるカメラです。PerspectiveCameraインスタンスのfovプロパティーを設定することで、カメラの視野角を変更できます。視野角とはカメラが映し出せる範囲のことです。

## OrthographicCamera