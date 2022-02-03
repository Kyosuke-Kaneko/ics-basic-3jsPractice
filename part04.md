# カメラ
Three.jsにはCamera3Dクラスがあることを、入門編で紹介しました。このCamera3Dがどのようにして利用できるのか、もう少し掘り下げて学んでみましょう。

Three.jsにさまざまな種類のカメラが搭載されています。

カメラの種類

 - THREE.PerspectiveCamera : 遠近感が適用されるカメラ
 - THREE.OrthographicCamera : 平行投影が適用されるカメラ

本節ではPerspectiveCameraとOrthographicCameraの2種類を掘り下げて解説します。

## PerspectiveCamera
遠近感を表現できるカメラです。PerspectiveCameraインスタンスのfovプロパティーを設定することで、カメラの視野角を変更できます。視野角とはカメラが映し出せる範囲のことです。

人間の見え方に近い表現

```js
// new THREE.PerspectiveCamera(視野角, アスペクト比, near, far)
const camera = new THREE.PerspectiveCamera(45, width / height, 1, 2000);
```

fovプロパティーは次の書式で変更できます。単位は角度です。ちなみに、fovはField of View＝視野角の頭文字の略語です。

```js
camera.fov = 60; 
```
PerspectiveCameraの第一引数が優先されるかも？
[https://threejs.org/docs/#api/en/cameras/PerspectiveCamera](https://threejs.org/docs/#api/en/cameras/PerspectiveCamera)

## OrthographicCamera
OrthographicCameraは平行投影を表現できるカメラです。このカメラには遠近感がないので、手前にある3Dオブジェクトも奥にある3Dオブジェクトも同じ大きさで表示されます。

規則正しく3Dオブジェクトを配置すると、平行投影のゲームのような表現が得られます。

2Dの表現とかにも使えるらしい。

[https://threejs.org/docs/#api/en/cameras/OrthographicCamera](https://threejs.org/docs/#api/en/cameras/OrthographicCamera)

## クリッピング
3D空間に存在するすべてのポリゴンをレンダリングするとパフォーマンスをムダに使ってしまうので、クリッピングという機能がレンズには備わっています。カメラから見て一定距離区間の間に存在するオブジェクトだけをレンダリングし、その距離の区間の外のオブジェクトはレンダリングしないというしくみです。クリッピングは次の2つのプロパティーで制御されます。

プロパティー

 - near : クリッピングする区間の開始距離
 - far : クリッピングする区間の終了距離

Three.jsではnearのデフォルト値は1、farのデフォルト値は2000に設定されています。とくにfarの値はかなり小さく設定されていますので、必要に応じて大きな値に変更するとよいでしょう。