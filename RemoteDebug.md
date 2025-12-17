<!--# **Visual Studio 2026** リモートデバッグ設定-->
# 対象読者
 AviUtl2を例にとったリモートデバッグ設定ですが、一般的なリモートデバッグに興味のある方向けです。 
 AviUtl2のリモートデバッグは特殊な事情があります。AviUtl2が利用するプラグインをデバッグする為、リモートのAviUtl2が前提としているフォルダにプラグインを転送し、リモートのAviUtl2を起動し、それにアタッチしなければなりません。  
 その辺りひと手間かかっています。  
 リモートデスクトップでAviUtl2を操作しながらデバッグする事も出来ます。リモートデバッグのいい所は、ブレークポイントがヒットしてもフォーカスチェンジが起きない事です。  
 # 事前準備  
 「Remote Tools for Visual Studio 2026」をMicrosoftのサイトから探して、リモートのPCにインストールしておく。
# お勧め  
リモートのPCには予めリモートデスクトップでアクセスできるようにしておくと、１つのキーボードと１つのマウスで、リモート、ローカル双方にアクセスでき便利です。

# 設定例 
  設定例1  
![構成図](https://github.com/NewGoldSmith/AviUtl2_RBF_Input_Plugin/blob/main/Images_RemoteDebug/01Properties.png?raw=true)  

これは、リモートでRBFReader.aui2をデバッグする設定です。
追加の配置ファイルとして「CommonConfigDlg.dll」が設定されています。  

※現在のソースでは実際は「CommonConfigDlg-Debug.dll」というファイルが生成されます。随時変更がなされる可能性がありますので、その辺りは各自対処をお願いします。  
  
このソリューションは以下のリンクです。    
[リンク](https://github.com/NewGoldSmith/AviUtl2_RBF_Input_Plugin)  

設定例2  
![構成図](https://github.com/NewGoldSmith/AviUtl2_RBF_Input_Plugin/blob/main/Images_RemoteDebug/03Properties2.png?raw=true)  
これはEXEファイルの例です。配置するディレクトリがない場合、自動で作られます。事前に権限を与えておいてください。  
## トラブルシューティング
- **接続出来ているような感触が無い**  
・pingを双方向から打ってみましょう。リモートへの反応がないなら、Windowsの次の設定を確認してみて下さい。  
![構成図](https://github.com/NewGoldSmith/AviUtl2_RBF_Input_Plugin/blob/main/Images_RemoteDebug/02rejection.png?raw=true)  
リモートデスクトップの接続が出来ていても、これがONになっていたら接続できません。OFFにします。  
- **リモートに配置自動で配置されてない**  
・構成で配置が設定されていない可能性があります。以下を参考にして下さい。  
![alt text](
https://github.com/NewGoldSmith/AviUtl2_RBF_Input_Plugin/blob/main/Images_RemoteDebug/05Composition.png?raw=true)  
# まとめ  
たまにリモートデバッグの設定を行うと、なかなかうまくいかない事がある。  
どこかに書き留めて置けば、次回はスムースに出来るであろうと思われる。

読者様に置かれましては、この記事が参考になりましたら幸いです。

