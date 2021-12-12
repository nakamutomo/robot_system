# robot_system_myled

2021年度ロボットシステム学の課題1で作成したデバイスドライバです。

入力数字された数字に応じてLEDが点灯・消灯します。

___


## 動作環境

- Raspberry Pi 4

- OS  :  ubuntu 20.04 server
 
___

## 使用したもの
- Raspberry Pi 4 × 1

- LED × 1

- 電子ブザー × 1

- 抵抗(220Ω) × 1

- ブレッドボード × 1

- ジャンパー線（オスメス）× 2

- ジャンパー線（オスオス）× 2

___

## 回路（pin情報）


- 回路図

<img src  = "" width = "720">


- 配線図

<img src = "" width = "720">


- pin情報
 
<img src="" width = "720">


- LED（赤色）:  22（GPIO25）

___



## 使用方法

#### 【インストール】
以下のコマンドを実行してください。

```
$ git clone https://github.com/nakamutomo/robot_system.git

$ cd robot_system

$ make

$ sudo insmod myled.ko

$ sudo chmod 666 /dev/myled0
```
___

#### 【アンインストール】
以下のコマンドを実行してください。

```
$ sudo rmmod myled

$ make clean
```
___

#### 【実行】
 
 インストール後に以下のコマンドを実行してください。
 ___
 
 ##### すべての動作を停止する
```
$ echo 0 > dev/myled0
```
___
 
##### LEDを点灯させ、ブザーを鳴らす
```
$ echo 1 > /dev/myled0
```
___

##### LEDを点灯させ、ブザーを鳴らしながら「私は元気です（watasihagennkidesu）」とモールス信号を打つ
```
$ echo  > dev/myled0
```
___

## デモ動画

https://youtu.be


___

## ライセンス
  [GNU General Public License v3.0](https://github.com/nakamutomo/robot_system/blob/main/COPYING)
