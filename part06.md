# スプライト
3Dでスプライトとは常に正面を向く3Dオブジェクトのことを言います。別の言い方でビルボードとも呼びます。今まで紹介した形状の3Dオブジェクトは角度の変化をつけることでさまざまな「向き」が表現されていました。ここで紹介するスプライトはどの視点から見ても常に正面を向いています。

スプライトはポリゴン数を節約するのには効果的です。とくにパーティクル表現では煙などの小さなオブジェクトを大量に生成するため負荷が増大しがちですが、こういう表現にもスプライトは有効です。

## 設定方法
Three.jsではTHREE.Spriteクラスのインスタンスを作成することで、ビルボードの表現ができます。THREE.SpriteはTHREE.Object3Dクラスのサブクラスであり、任意のマテリアルをコンストラクターで設定し、3D空間にadd()メソッドで追加して画面に表示します。

```js
// マテリアルを作成する
const material = new THREE.SpriteMaterial({
  map: new THREE.TextureLoader().load(/*画像パス*/),
});

const sprite = new THREE.Sprite(material);
scene.add(sprite);
```

THREE.Spriteクラスは常にカメラに向かって正面を向くため、角度に関するプロパティー（例：rotation）を変更したりメソッド（例：lookAt()）を実行しても表示に影響はありません。

マテリアルを作成して、シーンにaddする

## fogの適用
スプライトに対してフォグを有効にするにはTHREE.SpriteMaterialのfogプロパティーを有効にします。

```js
// マテリアルを作成する
const material = new THREE.SpriteMaterial({
  map: new THREE.TextureLoader().load(/*画像パス*/),
});
// マテリアルでフォグを有効にする
material.fog = true;

const sprite = new THREE.Sprite(material);
scene.add(sprite);
```