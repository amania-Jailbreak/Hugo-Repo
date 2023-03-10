---
title: "Pibrary"
date: 2022-12-31T15:14:55+09:00
image: https://github.com/amania-Jailbreak/amania-jailbreak.github.io/raw/master/Pibrary-Hed.png
author: "amania"
tags: ["Python", "CasioTweaks","Software"]
---

PibraryとはPythonで作成されたビルドされていないOSSソフトウェアを動かすためのソフトになります
Pibraryを使用すれば
- Pythonでビルド(exeにコンパイル)などをせずに配布することができます
- Pythonの仮想環境もどきが作れます(アプリケーションごとに環境が生成されその中にモジュールがインストールされます 仮想環境のみでは使用できません)

PibraryにはPython3.10 pipが同梱されておりモジュールは標準の状態から手を加えておらず
Pibraryに必要なモジュールは別の場所に隔離されていますのでPythonにほかのモジュールはインストールされていません
## 仕組み
PibraryはEelとElectronによって実現しています
.pa拡張子をアプリ内で指定しインストールするとpaの中にあるtxtファイルからモジュールをそのアプリ専用のフォルダにインストールしアプリを実行するときはそこからモジュールをインポートするように指定しますインストールしたフォルダ内にあるmain.pyのmain関数を実行します(main関数はなくても大丈夫ですがPibrary内部でエラーが発生します 支障はありません)
(Pibrary本体もビルドされていないため簡略化した方法で同じように起動します)

## paファイル
Pibraryにpaファイルを使用してアプリケーションをインストールします 
```
[appname].pa
 |- [app-identifier] (appfoldername)
 |- appinfo.ini (App information)
 |- requirements.txt (Required modules)
```
このようなフォルダ構造になっておりapp-identifierにはappinfoに記述したidentifierと同じ名前にします この中にアプリ本体を配置しモジュールとアプリ情報を記載しzip形式で圧縮して.pa拡張子にします

## appinfo.ini
Pibraryがアプリを管理するためにインストール時に読み取る情報が書かれているファイルです
```
[識別子]
name = アプリ名
developer = 開発者名
description = 詳細
icon = iconURL
identifier = 識別子
```
## Download
### Pibrary public beta(PB)
[Download Ver 1.0PB](https://bowlroll.net/file/287289)

### Pibrary stable
しばらくお待ちください

