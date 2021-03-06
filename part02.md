# ライト
Three.jsにはさまざまなライトが用意されています。

はじめのうちは、パラメーターの少ないAmbientLightやDirectionalLightを使い、慣れてきたらPointLightやSpotLightを使って表現を高めていくのがいいでしょう。

ライトは基本的に色、光の強さを元に決めていく。

## AmbientLight(環境光源)
AmbientLightクラスは環境光源を実現するクラスです。3D空間全体に均等に光を当てます。一律に明るくしたいときに使うといいでしょう。陰影や影(cast shadow)ができないので、この光源だけだと立体感を表現することはできません。たいてい、他のライトと一緒に利用します。

[https://threejs.org/docs/#api/en/lights/AmbientLight](https://threejs.org/docs/#api/en/lights/AmbientLight)

## DirectionalLight(平行光源)
DirectionalLightクラスは特定の方向に放射される光。光源は無限に離れているものとして、そこから発生する光線はすべて平行になります。わかりやすい利用例としては、太陽の光です。太陽は地球から遠く離れているので、その位置は無限であるとみなすことができます。太陽から地表に降り注ぐ光線は平行となります。<br>
一定の方向から当てられている光

[https://threejs.org/docs/#api/en/lights/DirectionalLight](https://threejs.org/docs/#api/en/lights/DirectionalLight)

## HemisphereLight(半球光源)
HemisphereLightクラスはAmbientLightクラスに似ていますが、上からの光の色と下からの光の色を分けられます。下からの光は反射光として、屋外での光の見え方に近くなります。

[https://threejs.org/docs/#api/en/lights/HemisphereLight](https://threejs.org/docs/#api/en/lights/HemisphereLight)

## PointLight(点光源)
PointLightクラスは単一点からあらゆる方向から放射される光源です。わかりやすい例としては、裸電球です。裸電球は周辺を明るくします。

[https://threejs.org/docs/#api/en/lights/PointLight](https://threejs.org/docs/#api/en/lights/PointLight)

## SpotLight
SpotLightクラスは、単一の点から一方向に放出され、円錐に沿って放出される光源です。わかりやすい例としては懐中電灯や、ステージのスポットライトを想像するといいでしょう。減衰率や光の方向の指定ができるので、指定できるパラメーターも多いです。たくさん配置すれば立体感・臨場感が生まれます。

[https://threejs.org/docs/#api/en/lights/SpotLight](https://threejs.org/docs/#api/en/lights/SpotLight)

## RectAreaLight(矩形光源)

RectAreaLightクラスは、面を横切って矩形平面に均一に放出される光源です。明るい窓やストリップ照明のようなものをシミュレートするために使用できます。

[https://threejs.org/docs/#api/en/lights/RectAreaLight](https://threejs.org/docs/#api/en/lights/RectAreaLight)

RectAreaLightUniformsLib.jsはいまいちわからなかった