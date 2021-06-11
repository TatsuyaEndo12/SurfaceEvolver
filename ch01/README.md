# ベシクルモデルの作成とv、daのパラメータ変化による変形
## ベシクルモデルの作成（曲げ弾性エネルギーを定義）
ベシクルの平衡形状は曲げ弾性エネルギーを最小化する形状として計算できる。
プログラム上では後述の{V;u;g}というコマンドでこの計算が実行される。
BCモデルの曲げ弾性エネルギーは以下のように表される。


<img src="https://github.com/TatsuyaEndo12/SurfaceEvolver/blob/patch1/ch01/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%202021-06-10%2014.51.19.png" width=25%>

<!--
![図1](https://user-images.githubusercontent.com/85602161/121469359-50860e80-c9f7-11eb-8a98-dbac001b84ee.png)



![図２](https://user-images.githubusercontent.com/85602161/121470063-92fc1b00-c9f8-11eb-8d51-fcb409049551.png)

ここではない
![test1](ch01/Github_ch01.pdf,"test1")
[Github_ch01.pdf](https://github.com/TatsuyaEndo12/SurfaceEvolver/files/6621284/Github_ch01.pdf)
[Github_test1.pdf](https://github.com/TatsuyaEndo12/SurfaceEvolver/files/6621705/Github_test1.pdf)
-->

![スクリーンショット 2021-06-11 15 00 02](https://user-images.githubusercontent.com/85602161/121638432-edaf7880-cac5-11eb-9545-404d8d535585.png)

![スクリーンショット 2021-06-10 15 12 00](https://user-images.githubusercontent.com/85602161/121473877-41ef2580-c9fe-11eb-934a-b44edd0c2a62.png)

![スクリーンショット 2021-06-11 15 09 48](https://user-images.githubusercontent.com/85602161/121639159-17b56a80-cac7-11eb-9bb4-3648fbf376db.png)

## 換算体積v(拘束条件)について
![スクリーンショット 2021-06-11 15 20 13](https://user-images.githubusercontent.com/85602161/121640175-8fd06000-cac8-11eb-9b4a-d66da4da612c.png)

![スクリーンショット 2021-06-11 15 30 17](https://user-images.githubusercontent.com/85602161/121641293-f7d37600-cac9-11eb-8eaa-76f29d424c68.png)

## 実際の動き（換算体積vを変化させる時）
![スクリーンショット 2021-06-11 15 36 07](https://user-images.githubusercontent.com/85602161/121641927-c7d8a280-caca-11eb-89cf-b0072d01a360.png)

## 膜面積差da（拘束条件）について
![スクリーンショット 2021-06-11 16 23 08](https://user-images.githubusercontent.com/85602161/121647538-797ad200-cad1-11eb-9f6a-a05a5d027070.png)

![スクリーンショット 2021-06-11 16 25 50](https://user-images.githubusercontent.com/85602161/121647741-b8108c80-cad1-11eb-82f6-ea990c7423ee.png)

![スクリーンショット 2021-06-11 16 27 36](https://user-images.githubusercontent.com/85602161/121648038-04f46300-cad2-11eb-8835-c5098b6974fc.png)

![スクリーンショット 2021-06-11 16 29 14](https://user-images.githubusercontent.com/85602161/121648180-2fdeb700-cad2-11eb-8420-c33a3e6cb2e3.png)

![スクリーンショット 2021-06-11 15 57 53](https://user-images.githubusercontent.com/85602161/121644303-d1173e80-cacd-11eb-9395-282926bea370.png)



