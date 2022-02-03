# スクリーン座標
Three.jsのcanvas要素にHTMLの表示を重ねたい時があります。

そのときに必要となるのが、canvas要素上のオブジェクトの座標です。これは、描写面であるcanvas要素上の座標のことなので、スクリーン座標と言います。

ワールド座標がthreeの生成されるシーンの原点から座標でスクリーンが生成されるキャンバスからの座標

## 取得方法
THREE.Cameraクラスのproject()メソッドを使うことで、ステージ上のXY座標に変換できます。

```js
// object3D は任意の3Dオブジェクト。
// 3Dオブジェクトのワールド座標を取得する
const worldPosition = object3D.getWorldPosition(new THREE.Vector3());
// スクリーン座標を取得する
const projection = worldPosition.project(camera);
```

project()メソッドの戻り値はTHREE.Vector3D型で、xとyはそれぞれ-1.0～+1.0の値をとります。zは3Dオブジェクトの深度を示します。ワールド座標を計算する必要があるので、計算対象の3Dオブジェクトはシーンに追加されている必要があります（シーン直下でなくても問題ありません）。

2D座標の取得には、rendererインスタンスの幅・高さの値を計算することでcanvas要素の左上からの座標を求めることができます。

```js
const object3D = new THREE.Mesh(); // 任意の3Dオブジェクト
const width = 960; // rendererの仮サイズ（利用場面において適したサイズに変更ください）
const height = 540;

// 3Dオブジェクトのワールド座標を取得する
const worldPosition = object3D.getWorldPosition(new THREE.Vector3());
// スクリーン座標を取得する
const projection = worldPosition.project(camera);
const sx = (width / 2) * (+projection.x + 1.0);
const sy = (height / 2) * (-projection.y + 1.0);

// スクリーン座標
console.log(sx, sy);
```

ワールド座標を取得してからスクリーン座標を取得する。
シーンから見るのか、キャンバスからみて計算するのか