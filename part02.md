# ライト
Three.jsにはさまざまなライトが用意されています。

はじめのうちは、パラメーターの少ないAmbientLightやDirectionalLightを使い、慣れてきたらPointLightやSpotLightを使って表現を高めていくのがいいでしょう。

## AmbientLight(環境光源)
AmbientLightクラスは環境光源を実現するクラスです。3D空間全体に均等に光を当てます。一律に明るくしたいときに使うといいでしょう。陰影や影(cast shadow)ができないので、この光源だけだと立体感を表現することはできません。たいてい、他のライトと一緒に利用します。

[https://threejs.org/docs/#api/en/lights/AmbientLight](https://threejs.org/docs/#api/en/lights/AmbientLight)

## DirectionalLight(平行光源)
DirectionalLightクラスは特定の方向に放射される光。光源は無限に離れているものとして、そこから発生する光線はすべて平行になります。わかりやすい利用例としては、太陽の光です。太陽は地球から遠く離れているので、その位置は無限であるとみなすことができます。太陽から地表に降り注ぐ光線は平行となります。<br>
一定の方向から当てられている光

[https://threejs.org/docs/#api/en/lights/DirectionalLight](https://threejs.org/docs/#api/en/lights/DirectionalLight)