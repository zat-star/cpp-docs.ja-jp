---
title: "Windows フォームと MFC のプログラミング上の違い | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC [C++], Windows フォームのサポート"
  - "Windows フォーム [C++], 比較 (MFC との)"
ms.assetid: f3bfcf45-cfd4-45a4-8cde-5f4dbb18ee51
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows フォームと MFC のプログラミング上の違い
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

「[MFC での Windows フォーム ユーザー コントロールの使用](../dotnet/using-a-windows-form-user-control-in-mfc.md)」のトピックでは、MFC による Windows フォームのサポートについて説明しています。  .NET Framework または MFC でのプログラミングにあまり慣れていない場合は、このトピックで、.NET Framework と MFC のプログラミング上の違いに関する背景情報を参照してください。  
  
 Windows フォームは、.NET Framework で Microsoft Windows アプリケーションを作成する場合に使用します。  このフレームワークに用意された、オブジェクト指向の、拡張性がある最新のクラスの集合を使用すると、Windows ベースの強力なアプリケーションを開発できます。  Windows フォームを使用すると、さまざまなデータ ソースにアクセスし、Windows フォーム コントロールでデータを表示および編集できる、リッチ クライアント アプリケーションを作成できます。  
  
 ただし、MFC を使い慣れている開発者は、Windows フォームでまだ明示的にサポートされていない種類のアプリケーションを作成することに慣れている場合があります。  Windows フォーム アプリケーションは、MFC ダイアログ アプリケーションとほぼ同等です。  しかし、Windows フォーム アプリケーションには、OLE ドキュメント サーバー\/コンテナー、ActiveX ドキュメントなどの他の種類の MFC アプリケーションを直接サポートするインフラストラクチャが用意されていません。また、シングル ドキュメント インターフェイス \(SDI\)、マルチ ドキュメント インターフェイス \(MDI\)、およびマルチ トップレベル インターフェイス \(MTI\) のドキュメント\/ビューもサポートしません。  プログラマは、独自のロジックを記述してこれらのアプリケーションを作成できます。  
  
 Windows フォーム アプリケーションの詳細については、「[Windows フォームの概要](../Topic/Windows%20Forms%20Overview.md)」を参照してください。  
  
 Windows フォームと MFC の組み合わせ示すサンプル アプリケーションについては、["MFC and Windows Forms Integration \(MFC Windows フォームとの統合\)"](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)を参照してください。  
  
 Windows フォームには、次の MFC ビュー\/ドキュメント、およびコマンド ルーティングに相当する機能がありません。  
  
-   シェル統合機能  
  
     MFC は、ドキュメントを右クリックして \[開く\]、\[編集\]、\[印刷\] などの動詞を選択したときにシェルで使用されるダイナミック データ エクスチェンジ \(DDE: Dynamic Data Exchange \) コマンドとコマンド ライン引数を処理します。  Windows フォームにはシェル統合機能がないため、Windows フォームはシェルの動詞に応答しません。  
  
-   ドキュメント テンプレート  
  
     MFC では、ドキュメント テンプレートを使用して、MDI モード、SDI モード、または MTI モードのフレーム ウィンドウに含まれているビューを、プログラマが開いたドキュメントに関連付けます。  Windows フォームには、ドキュメント テンプレートに相当する機能がありません。  
  
-   ドキュメント  
  
     MFC はドキュメント ファイルの種類を登録し、シェルからドキュメントを開くときにドキュメントの種類を処理します。  Windows フォームはドキュメントをサポートしません。  
  
-   ドキュメントの状態  
  
     MFC はドキュメントをダーティな状態で維持します。  このため、MFC アプリケーションを終了するとき、MFC アプリケーションを含む最後のビューを閉じるとき、または Windows を終了するときに、ドキュメントを保存するように指示されます。  Windows フォームでは、これに相当する機能がサポートされていません。  
  
-   コマンド  
  
     MFC には、コマンドの概念があります。  メニュー バー、ツール バー、およびコンテキスト メニューのどれを使用しても、\[切り取り\] や \[コピー\] などの同じコマンドを呼び出すことができます。  Windows フォームでは、コマンドはメニュー項目などの特定の UI 要素に密接に関連付けられたイベントであるため、すべてのコマンド イベントを明示的にフックする必要があります。  Windows フォームでは、単一のハンドラーで複数のイベントを処理することもできます。  詳細については、「[Windows フォームの 1 つのイベント ハンドラーに対する複数のイベントの関連付け](../Topic/How%20to:%20Connect%20Multiple%20Events%20to%20a%20Single%20Event%20Handler%20in%20Windows%20Forms.md)」を参照してください。  
  
-   コマンド ルーティング  
  
     MFC のコマンド ルーティングを使用すると、アクティブなビューまたはドキュメントでコマンドを処理できます。  多くの場合、コマンドの意味はビューの種類によって異なるため \(たとえば、テキスト エディット ビューの \[コピー\] の動作とグラフィックス エディターの \[コピー\] の動作\)、コマンドはアクティブなビューで処理する必要があります。  Windows フォームのメニューとツール バーでは、アクティブなビューを同様の方法で扱うため、追加の内部コードを記述しない限り、ビューの種類に応じて異なるハンドラーを使用して **MenuItem.Click** イベントを処理することはできません。  
  
-   コマンド更新機構  
  
     MFC にはコマンド更新機構があります。  このため、アクティブなビューまたはドキュメントが、UI 要素の状態 \(メニュー項目やツール ボタンの有効化\/無効化、チェック状態など\) を管理します。  Windows フォームには、コマンド更新機構に相当する機構がありません。  
  
## 参照  
 [MFC での Windows フォーム ユーザー コントロールの使用](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Windows Forms Walkthroughs](http://msdn.microsoft.com/ja-jp/fd44d13d-4733-416f-aefc-32592e59e5d9)