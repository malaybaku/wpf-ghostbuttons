### WPF-Ghostbutton

### Overview
ゴーストボタンのWPF実装です。一部実装としてイマイチな完成度のモノがあるのでご注意下さい。

### License
ブログ記事に載せてるコードと同レベルの扱いで公開しており、著作権を主張しません。また本コードの利用による損害の責任は一切負いません。

### 動作環境
Windows 7/8.1で確認済みです。.NET Framework 4.5以降が必要です。

### 使い方
MainWindow.xaml自体が利用方法のサンプルになっているのでご確認下さい。例えば影が付くボタンは

```
<Button Style="{StaticResource ShadowButton}" ... />
```

というスタイル指定で設定されており、スタイルのロードは`GhostButtons.xaml`で、各スタイルの定義は`ButtonStyles`フォルダ以下の各ファイルで行われています。

### 注意
[MSDN](https://msdn.microsoft.com/ja-jp/library/ms753328%28v=vs.110%29.aspx)ではボタンの`VisualState`について`FocusStates`グループや`ValidationStates`があることが触れられていますが、ココで作っているゴーストボタンではこれらのグループは実装されていません。本プロジェクトで作られたゴーストボタンは`CommonStates`グループの`Normal`,`MouseOver`,`Pressed`のみを実装しています。

またスタイルのうち`CircleFromCenterButton`と`EchoLikeCircleButton`を使用した場合、あまり大きなボタンを作ると円が広がるエフェクトがボタン外まで伸びきらない場合があります。円形エフェクトのサイズは`CircleFromCenterButton.xaml`および`EchoLikeCircleButton.xaml`の初頭にある`EllipseMaxWidth`という定数で指定されているので、大きなボタンを使いたい場合はこのパラメータを変更して下さい。なお、このように定数を使用しているのはテンプレートのアニメーションにバインディングを適用するのが難しいという事情があるためです。


### Contact
Web Page: http://www.baku-dreameater.net/

