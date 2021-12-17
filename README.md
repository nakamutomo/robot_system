# robot_system

2021年度ロボットシステム学の課題1で作成したデバイスドライバです。

入力された数字に応じてLEDが点灯・消灯し、それに合わせてブザーが鳴ります。

___


## 動作環境

- Raspberry Pi 4

- OS  :  ubuntu 20.04 server
 
___

## 使用したもの
- Raspberry Pi 4 × 1

- LED × 1

- 電磁ブザー × 1

- ブレッドボード × 1

- ジャンパー線（オスメス）× 2

- ジャンパー線（オスオス）× 1

___

## 回路（pin情報）


- 回路図

<img src  = "https://user-images.githubusercontent.com/76559344/145761914-6399beee-e207-4666-b481-769b5801aef5.png" width = "720">


- 配線図

<img src = "https://user-images.githubusercontent.com/76559344/145755819-d2802e5f-b799-4224-9483-9d0adee4a8d0.jpg" width = "720">
<img src = "https://user-images.githubusercontent.com/76559344/145755968-eb20745e-15e9-40b6-a23d-2887c1e1ac61.jpg" width = "720">


- pin情報
 
<img src="https://user-images.githubusercontent.com/76559344/146491120-6666cf5c-5893-43f1-9d3d-88812d54b4ff.png" width = "720">


- LED　:  22（GPIO25）

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
$ echo 0 > /dev/myled0
```
___
 
##### LEDを点灯させ、ブザーを鳴らす
```
$ echo 1 > /dev/myled0
```
___

##### LEDを点灯させ、ブザーを鳴らしながら「私は元気です（watasihagennkidesu）」とモールス信号を打つ
```
$ echo 2 > /dev/myled0
```
___

## デモ動画

https://youtu.be/G7M4QSpYUgs


___

## ライセンス
  [GNU General Public License v3.0](https://github.com/nakamutomo/robot_system/blob/main/COPYING)
  

___

## 参考
  [参考にさせていただいた方のREADME](https://github.com/ryuseiiiii/robosys_device_drivers/blob/main/README.md)
  
  [pin情報の作成時に参考にさせていただいた方のサイト](https://techhobby.net/2020/04/13/raspberry-pi%E3%81%AEgpio%E3%83%94%E3%83%B3%E3%81%AE%E9%9B%BB%E6%B0%97%E7%9A%84%E4%BB%95%E6%A7%98/)

