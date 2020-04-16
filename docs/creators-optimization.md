---
id: spoke-optimization
title: Optimizing Scenes
---

## パフォーマンスを改善する

Hubsシーンを構築する場合、高火力な有線式VRヘッドセットや省電力の携帯電話といった多種多様なデバイス上で適切に実行される必要があります。
シーンのパフォーマンスは、デバイスのタイプとビジターの接続速度に応じて異なる場合があります。

あらゆるビジターにとってのパフォーマンスを向上させるひとつの方法は、シーンの複雑さを軽減することです。
シーン内のオブジェクトの数を減らしたり、使用しているアセットを最適化したりすることで改善します。
次のセクションでは、アセットを最適化するためにできる手順について簡単に説明します。

### パフォーマンスの測定

シーンのパフォーマンスを詳しく見るには、VR ステータスメニューを開きます。
デスクトップの右下にある FPS メーターをクリックします（VR の場合はチャットボックスに /vrstats と入力します）。
これにより、シーンのロード時間、三角形の数、テクスチャに関する追加情報が表示されます。

<!-- Insert video of opening performance tools -->

### 画像と動画の最適化

非常に大きく詳細な画像や動画は、ウェブ上でのパフォーマンスを低下させる可能性があります。シーンにこの種のメディアが多く含まれている場合、パフォーマンスを維持するために以下のことを行うことができます。

* 大きな画像/ビデオのサイズを小さくする
* ファイルを圧縮する、画像の場合はPhotoshopの "web用に保存" 機能を使用する、またはオンライン画像や動画の圧縮ツールを使用してファイルサイズを縮小する。
* .png 画像から .jpeg に変換してみてください。ファイルサイズが小さくなる場合があります。
* GIF をビデオ形式に変換してください。Hubs内でより効果的に動作します。

### 3Dモデルの最適化

複雑な3Dモデルは、シーン内でパフォーマンス問題を引き起こす可能性があります。
オブジェクトの複雑性に関わる2つの要素がありますが、1つ目はモデル内のテクスチャアセット、
2つ目は、モデル自体のポリゴンの数です。
一般的に、モデルがよりリアルに見えるほど、モデルはより複雑になります（これは必ずしもそうとは限りませんが）。

SpokeやHubs内でSketchfabやGoogle Polyブラウザを使用して見つかる3Dモデルは、オブジェクトのサイズや複雑さに基づいて、すでにフィルタリングされています。
しかし、別のダウンロード可能なモデルのパフォーマンスを向上させたい場合は、オブジェクトのテクスチャサイズを小さくするか、ポリゴンの数を減らすことで改善できます。
これには [Blender]() のようなツールを使うことができます。


#### Reduce texture size

To reduce the image texture size of a glb model, you can either [covert to a gltf file](), so that there is a folder with all the texture files and reduce the size of the image textures using a tool like photoshop (reduce the size of the images by half, or by a quarter for example). 

We've also made a [video of other things you can do to optimize the size of your textures in Blender](https://www.youtube.com/watch?v=6uhAp1m1SXQ).

#### Reduce number of triangles

There is no golden rule of thumb for what number of triangles in a model is ideal, however, we recommend using models with only tens of thousands, rather than hundreds of thousands of triangles. Many complex 3D models can have their triangle count reduced without greatly impacting the way that the model looks. You can do this using the Mesh Decimation tool in Blender. For instructions, check out [this video](https://www.youtube.com/watch?v=IIQNj-6_tQE_)

## Oculus Quest & Mobile Notes

Note that some scenes might look different 



<!-- 
## Developing for Mobile Devices & Quest


### AO


gifs can be hard on your scene -->
