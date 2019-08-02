# debug_report

※一部画像の文字が小さくてとても見にくいです

## ブレークポイント

### ブレークポイントとは  
実行中のプログラムブレークポイントを置いた位置で止めて状態を確認し、不具合の原因などを探るために用いられる。

### どのような時に使うといいのか  
プログラムに不具合が発生している時、その時の値の中身が書き換わっているかなど


### ブレークポイントの使い方  
カーソルで気になる所を押しそこでF9を押します。  
そうすると左側に赤い丸が表示されます。  
そのままF5を押すと先ほど置いた、ブレークポイントの所でプログラムがストップしてその時の値に何が入っているかを表示してくれたりしてくれます。

　




### これを使っての効率化  
プログラムが実行できない時、または実行しても思っていたのと違うのが表示された時にこれを使うとどこで不具合がでているかを一つずつ確認するよりブレークポイントを使ったほうが早く分かります  



![](https://github.com/m-kazumasa/Picture/blob/master/2019-07-08%20(1).png?raw=true)  
  
ここでブレークポイントを使うと最後まで表示されずに止めた所まで表示されます 

![](https://github.com/m-kazumasa/Picture/blob/master/2019-07-08%20(5).png?raw=true)

つけずに実行すると最後まで表示される。
 ***

## Step over/in/out
Step over/in/outとは

### step　inとは
F１１で使います。  
下のGIFのように1単位ずつ下っていき一つずつ確認していきます。

![](https://github.com/hiroto1130/image_preservation/raw/master/step%20ovre%20in%20out/step%20over%20,%20in%20,%20out%201%20.gif?raw=true)

### step outとは
Shift+F11で使います。  
step inで別に中身を見たくない関数の中に入った時、  
無限ループの中に入って抜けたいときに使います。

### step　overとは
F10で使います。
確認したい関数が下にある場合step inだと一つずつ確認するので時間がかかりますが、step　overだと塊ごとに飛ばせるのですぐに下まで行くことができます。

***
## 自動変数・ローカル変数ウィンドウ

### 自動変数とは
自動変数ウィンドウには、現在のブレークポイントを使用し通過した変数が表示されます。  

![](https://github.com/m-kazumasa/Picture/blob/master/2019-07-09%20(3).png?raw=true)
  
  この画像の左下に書いてある通りa.bの中身に１０と１００が入っていて、まだCにはどこかの値（ゴミ）が入っています。

  ### ローカル変数とは
  ローカル変数ウィンドウとは見ている関数の中のローカル変数が全て表示される。

  ![](https://github.com/m-kazumasa/Picture/blob/master/2019-07-10.png?raw=true)

  この画像の左下に書いてある通りにaは通過したので、
  値は１０が入っていますがその他b,ｃにはどこかの値（ゴミ）が入っています。  
    
  このどちらも使用中に左下で値を変えることができますこの画像内であればa,b,c、の値を、普段入ることの無い関数を作った場合でもこのどちらかを使い値を任意に変えることが出来るのでとても便利です。
***
## ウォッチ式
ウォッチ式とは自分が見たい一つの変数を入力して値を見るとこが出来る。
***

## データブレーイクポイント

変わるはずのない変数の値が変わっていたり
突然プログラムが強制終了したりします。
そんな時に予想される不具合がメモリ破壊です。

メモリ破壊は破壊直後に落ちずに、破壊したメモリが参照されるときに初めて不具合が分かる事が多いので、不具合の原因を調査するのが困難です。

そういった時にデータブレークです。
データブレークとは指定したアドレスの内容が変わった時にブレークするデバッグ機能の事です。
使い方ですが

任意の場所でブレークポイントを置いてプログラムを中断させる
メニューバーのデバッグ   ブレークポイントの作成   
データブレイクポイントをクリックする
データブレークポイントを設定するアドレスを入力する
![](https://github.com/m-kazumasa/Picture/blob/master/2019-07-10%20(1).png?raw=true)
![](https://github.com/m-kazumasa/Picture/blob/master/2019-07-10%20(2).png?raw=true)
***
## メモリウィンドウ
メモリウィンドウはブレークポイントで止めてからじゃないと開かないです。デバッグからウィンドウでメモリを押すと開きます。そこにアドレスを入れるとその中身が見れるようになります



***
## スタックメモリー
  

## スタックメモリとは
簡単なコードを書きます。
int a=1;
int b=2;
これを実行すると上から二つメモリが確保されます。
３つにするとメモリが３つ確保されます
***
## イミディエイトウィンドウ
プロシージャを全て作成しなくても簡単なステートメントを実行することができる場所です。
また変数の利用やコードに書かれたプロパティや変数の値を確認することもできます。
変数に別の値を代入したり、コードを使って多少命令を出すこともできますが、プログラムに影響を与えない範囲に限ります。
***
今回これらのデバッグ方法を調べながら書いているとブレークポイントとstepin/outは使ったことがあったので調べながら思いでして書いてました。
そのほかは全然分からなくて調べていても良く分からない事もあったのでやっぱり使ってみる事にしました。
