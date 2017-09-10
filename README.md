# openFrameworks on Android Studio

## 基本情報
+ 2017/09/07
+ Windows 10 64bit

## 1. Download and Install

### 1.1 Android Studioのインストール
Version: 2.3.3.0
https://developer.android.com/studio/install.html

### 1.2 Android NDK のインストール（r10b 以下）
Windows 64: http://dl.google.com/android/ndk/android-ndk-r10e-windows-x86_64.exe

### 1.3 MinGW のインストール
http://www.multigesture.net/articles/how-to-install-mingw-msys-and-eclipse-on-windows/.

上記に従い，PATHの設定を行う．

### 1.4 openFrameworksのダウンロード
of v0.9.3
http://openframeworks.cc/download/

※of v0.9.8だとReferenceにあるようにfind関数で躓いたので，of v0.9.3で進めた．

## 2. プロジェクトのインポート

Android StudioでOpen Projectを選択．libs/openFrameworksCompiled/project/android ディレクトリの build.gradleを指定する

## 3. PATHの設定

C:\Users\n.iwamoto\Desktop\oF_Android\of_v0.9.8_android_release\libs\openFrameworksCompiled\project\androidのlocal.propertiesとpaths.makeを変更

+ local.properties
      ndk.dir=C\:\\Users\\n.iwamoto\\Desktop\\oF_Android\\android-ndk-r10e
      sdk.dir=C\:\\Users\\n.iwamoto\\AppData\\Local\\Android\\Sdk

+ path.make
      NDK_ROOT=C\:\\Users\\n.iwamoto\\Desktop\\oF_Android\\android-ndk-r10e

## 4. classpathのバージョンを変更

    classpath 'com.android.tools.build:gradle:1.0.1'

    classpath 'com.android.tools.build:gradle:2.2.0'


## 5 VT-xの有効化

### 5.1 BIOSからのセッティング
F2を押して，VT-xを有効化

### 5.2 Intel Hardware Accelerated Execution Manager

http://every-rating.com/android/android-studiovt-xenableenable-vt-x-in-your-bios-security-settings.html

もしインストールされていても，いったんRemoveして再びインストールしたら行けた．



### 6. 参照設定
AndroidのLibraryが参照されてないみたいなことを言われるので，それを設定する

[AndroidでOpenFrameworksを使用する。](https://gist.github.com/ujhrkzy/52e0265c09d2639b7ee4)

    ofAndroidLibをインポートする。

    サンプルプロジェクトをインポートするとofxAndroidが参照できないとエラーがでるので、下記にあるofAndroidLibをインポートする。
    of_v0.8.4_android_release/addons/ofxAndroid/ofAndroidLib

### 7. ofxAndroidの更新

ofxAndroidのいくつかのソースファイルがおかしかったので，gitからダウンロードしたofxAndroidのソースコードを上書き
C:\Users\n.iwamoto\Desktop\oF_Android\of_v0.9.3_android_release\addons\ofxAndroid\ofAndroidLib\src\cc\openframeworks

### 8. 絶賛躓き中

ビルドが通り，アプリ起動まで至ったがアプリがすぐに落ちてその先に行けず...．
とりあえず，今後のoF側のAndroidサポートに期待するとする．

# Reference

+ [Android StudioでopenFrameworksをビルドする](http://qiita.com/chimanaco/items/093805fa18208378abb0)
+ その他，openFrameworksのコミュニティ系のページ
