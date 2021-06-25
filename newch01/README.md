# ベシクルモデルの作成と𝑣、daのパラメータ変化による変形
## ベシクルモデルの作成（曲げ弾性エネルギーを定義）
ベシクルの平衡形状は曲げ弾性エネルギーを最小化する形状として計算できる。
プログラム上では後述の{V;u;g}というコマンドでこの計算が実行される。
BCモデルの曲げ弾性エネルギーは以下のように表される。

![image](https://user-images.githubusercontent.com/85602161/122736919-7a72e700-d2bb-11eb-9b42-de3d88f89644.png)


ここで𝐻は曲面の平均曲率、 𝜅は膜弾性率。
半径 𝑅 の球状ベシクルについて，曲げ弾性エネルギー 𝑊を計算すると 、

半径 𝑅 の球状ベシクルにおける曲げ弾性エネルギー 𝑊 で規格化された曲げ弾性エネルギーwを

と表し、これをプログラムで定義すると以下のようなQUANTITYで表される。

![スクリーンショット 2021-06-25 15 38 39](https://user-images.githubusercontent.com/85602161/123381335-916f4d00-d5cb-11eb-9a99-6db2729d047d.png)


## 拘束条件(換算体積v)について
換算体積(reduced volume)はベシクルの持つ 膜面積 A から見た球状ベシクル(半径R<sub>0</sub>)の体積と実際の体積 V の比を表す無次元数であり、次のように定義される。


つまり、表面積Aを変化させることで換算体積vを変化させることができる。

換算体積を変化させるプログラムは以下の通り(ここで“rev”は任意の換算体積を意味する)。

farea.target := (body[1].target*6*(pi)**(1/2)/rev)**(2/3);

## 実際の動き（換算体積vを変化させる時）
SEを起動し、

と入力し、

と入力し、換算体積をずらしてから

と入力することで、パラメーターを変化させてのシミュレーションが行われる。Vは頂点を平均的に分布させる操作を実行し、uはスパイク防止の操作を実行、gは安定化計算を実行するがここでは3つのコマンドを1セットにして安定化計算を行なっている。
（上の例では1000回計算が行われる。）

## 拘束条件（膜面積差da）について
膜面積差(area difference)は二分子膜の外膜と内膜の面積差である。球状ベシクル(半径R<sub>0</sub>)の膜面積差ΔA<sub>sphere</sub>は以下のようになる。


表面積 A をもつベシクルの面積差は球状ベシクルの膜面積差ΔA<sub>sphere</sub>を
用いて，次のように規格化される。


膜面積差∆𝑎を表すプログラムは以下の通り。
mciを拘束条件に設定した上でdaの値を変化させることで膜面積差∆𝑎を変化させることができる。
mciはQUANTITYで定義されている。

![スクリーンショット 2021-06-25 15 41 09](https://user-images.githubusercontent.com/85602161/123381492-c7accc80-d5cb-11eb-8abc-7684c043d02f.png)


## 実際の動き（膜面積差daを変化させる時）
SEを起動し、

と入力し、mciを動かせるようにしてから

と入力し、mciを拘束条件に設定する。その後、

と入力することで、パラメーターを変化させてのシミュレーションが行われる。

## 課題
![スクリーンショット 2021-06-11 16 54 33](https://user-images.githubusercontent.com/85602161/121651639-ccef1f00-cad5-11eb-8aaa-6220d6b07d3a.png)
![スクリーンショット 2021-06-11 17 11 03](https://user-images.githubusercontent.com/85602161/121653817-0d4f9c80-cad8-11eb-8d27-6ef1c0c5b184.png)

![スクリーンショット 2021-06-11 17 25 01](https://user-images.githubusercontent.com/85602161/121655979-fca02600-cad9-11eb-978c-9a5534048d35.png)
![スクリーンショット 2021-06-11 17 27 37](https://user-images.githubusercontent.com/85602161/121656376-60c2ea00-cada-11eb-9890-dcc8e639f1e3.png)


![スクリーンショット 2021-06-11 17 21 44](https://user-images.githubusercontent.com/85602161/121655371-856a9200-cad9-11eb-8cc8-c9741dd0c141.png)
![スクリーンショット 2021-06-11 17 22 59](https://user-images.githubusercontent.com/85602161/121655610-b3e86d00-cad9-11eb-9696-855e5230bd49.png)

## 解答
![スクリーンショット 2021-06-11 16 54 33](https://user-images.githubusercontent.com/85602161/121651639-ccef1f00-cad5-11eb-8aaa-6220d6b07d3a.png)
![スクリーンショット 2021-06-11 17 11 03](https://user-images.githubusercontent.com/85602161/121653817-0d4f9c80-cad8-11eb-8d27-6ef1c0c5b184.png)
![スクリーンショット 2021-06-14 12 24 53](https://user-images.githubusercontent.com/85602161/121835179-8f73d700-cd0b-11eb-908a-05eb8b614169.png)
![スクリーンショット 2021-06-14 12 26 09](https://user-images.githubusercontent.com/85602161/121835260-bf22df00-cd0b-11eb-930c-76ffc87e076d.png)
![スクリーンショット 2021-06-14 12 27 24](https://user-images.githubusercontent.com/85602161/121835316-eaa5c980-cd0b-11eb-9722-8ae209cb48b4.png)

![スクリーンショット 2021-06-14 12 29 46](https://user-images.githubusercontent.com/85602161/121835427-3e181780-cd0c-11eb-9cf6-f50f9643f47b.png)
![スクリーンショット 2021-06-14 12 30 43](https://user-images.githubusercontent.com/85602161/121835486-61db5d80-cd0c-11eb-95fa-a1b992a65262.png)
![スクリーンショット 2021-06-14 12 53 28](https://user-images.githubusercontent.com/85602161/121836982-8b49b880-cd0f-11eb-99df-5963bf368312.png)
![スクリーンショット 2021-06-14 12 55 19](https://user-images.githubusercontent.com/85602161/121837107-cea42700-cd0f-11eb-87bf-b4f734577170.png)
