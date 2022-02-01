# さまざまなマテリアルクラス
マテリアルのプロパティーによってさまざまな質感の表現ができる

## MeshBasicMaterial
THREE.MeshBasicMaterialクラスはライティングを考慮しないマテリアルです。  ::陰がつかないので均一な塗りつぶした状態**になります。開発中にライティングを無視して、動作確認するときに役立つでしょう。


大体がTextureの設定（map）。aoのオブジェクトはambient oclusion map のこと。
### ambient occlusion
シーン内の環境光（ambient）がどの程度さえぎられている（occlusion）かを計算するレンダリング方法のこと。シーン内の1点から半球方向に対する光の遮蔽（しゃへい）状況を計算し、リアルな影を生成する。比較的少ない計算量で、柔らかな陰影を表現できる。特に明るい色のモデルの陰影を表現するのに有効である。

[https://threejs.org/docs/#api/en/materials/MeshBasicMaterial](https://threejs.org/docs/#api/en/materials/MeshBasicMaterial)

## MeshBasicMaterial
THREE.MeshNormalMaterialクラスはノーマルのカラーをRGBで可視化するマテリアルです。ライティングを必要としないため、手軽に動作確認するときに役立つでしょう。

[https://threejs.org/docs/#api/en/materials/MeshNormalMaterial](https://threejs.org/docs/#api/en/materials/MeshNormalMaterial)

## MeshLambertMaterial
THREE.MeshLambertMaterialクラスはランバート・シェーディングと言う、光沢感のないマットな質感を表現できるマテリアルです。陰がでるため奥行き感を表現できます。陰影を必要とするマテリアルなので、ライトが必要となります。

[https://threejs.org/docs/#api/en/materials/MeshLambertMaterial](https://threejs.org/docs/#api/en/materials/MeshLambertMaterial)

## MeshPhongMaterial
THREE.MeshPhongMaterialクラスはフォン・シェーディングと言う、光沢感のある質感を表現できるマテリアルです。

[https://threejs.org/docs/#api/en/materials/MeshPhongMaterial](https://threejs.org/docs/#api/en/materials/MeshPhongMaterial)

## MeshToonMaterial
THREE.MeshToonMaterialクラスはアニメのようなトゥーンシェーディングを実現できるマテリアルです。MeshPhongMaterialクラスの拡張として用意されています。

[https://ics.media/tutorial-three/material_variation/](https://ics.media/tutorial-three/material_variation/)


## MeshStandardMaterial
THREE.MeshStandardMaterialクラスは物理ベースレンダリングのマテリアルです。物理ベースレンダリングは多くの3Dアプリケーションで実装されているもので（UnityやUnrealなど）、光の反射や散乱など現実の物理現象を再現します。先述のMeshPhongMaterialやMeshLambertMaterialよりも調整できることが多く、現実味のある表現ができます。

roughnessプロパティーの値によって、光沢感の有無を調整できます。0のときは光沢の質感、1のときはマットな質感になります。

[https://threejs.org/docs/#api/en/materials/MeshStandardMaterial](https://threejs.org/docs/#api/en/materials/MeshStandardMaterial)