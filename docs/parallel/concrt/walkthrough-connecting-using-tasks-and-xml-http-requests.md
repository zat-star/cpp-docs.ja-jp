---
title: "チュートリアル: タスクおよび XML HTTP 要求を使用した接続 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "接続 (Web サービスに)、Windows ストア アプリ [C++]"
  - "IXMLHTTPRequest2 およびタスク、例"
  - "IXHR2 およびタスク、例"
ms.assetid: e8e12d46-604c-42a7-abfd-b1d1bb2ed6b3
caps.latest.revision: 16
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# チュートリアル: タスクおよび XML HTTP 要求を使用した接続
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この例では、[IXMLHTTPRequest2](http://msdn.microsoft.com/ja-jp/bbc11c4a-aecf-4d6d-8275-3e852e309908) および [IXMLHTTPRequest2Callback](http://msdn.microsoft.com/ja-jp/aa4b3f4c-6e28-458b-be25-6cce8865fc71) インターフェイスをタスクと合わせて使って、HTTP GET および POST 要求を [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリケーションの Web サービスに送信する方法を示しています。  タスクと `IXMLHTTPRequest2` を組み合わせることによって、他のタスクと共に構成するコードを記述できます。  たとえば、タスクのチェーンの一部としてダウンロード タスクを使用できます。  ダウンロード タスクは、処理が取り消された場合にも応答できます。  
  
> [!TIP]
>  また、C\+\+ REST SDK を使って、C\+\+ による [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリケーション、またはデスクトップの C\+\+ アプリから HTTP 要求を実行できます。  詳細については、「[C\+\+ REST SDK \(Codename "Casablanca"\)](../../top/cpp-rest-sdk-codename-casablanca.md)」を参照してください。  
  
 タスクの詳細については、「[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)」を参照してください。  [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリケーションでのタスクの使用方法の詳細については、「[Asynchronous programming in C\+\+](http://msdn.microsoft.com/ja-jp/512700b7-7863-44cc-93a2-366938052f31)」および「[C\+\+ における Windows ストア アプリ用の非同期操作の作成](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)」を参照してください。  
  
 このドキュメントでは、最初に `HttpRequest` およびそのサポート クラスを作成する方法を示します。  次に、C\+\+ および XAML を使用する [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリケーションからこのクラスを使用する方法を示します。  
  
 このドキュメントで説明している `HttpReader` クラスを使用する例の詳細については、「[JavaScript および C\+\+ での Windows ストア アプリ \(Bing Maps Trip Optimizer\) の開発](../Topic/Developing%20Bing%20Maps%20Trip%20Optimizer,%20a%20Windows%20Store%20app%20in%20JavaScript%20and%20C++.md)」を参照してください。  `IXMLHTTPRequest2` を使用し、タスクを使用しないもう 1 つの例については、「[Quickstart: Connecting using XML HTTP Request \(IXMLHTTPRequest2\)](http://msdn.microsoft.com/ja-jp/cc7aed53-b2c5-4d83-b85d-cff2f5ba7b35)」を参照してください。  
  
> [!TIP]
>  `IXMLHTTPRequest2` および `IXMLHTTPRequest2Callback` は、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリケーションで使用することをお勧めするインターフェイスです。  また、この例をデスクトップ アプリケーションでの使用に適用することもできます。  
  
## 必須コンポーネント  
  
## HttpRequest、HttpRequestBuffersCallback、および HttpRequestStringCallback クラスを定義する  
 `IXMLHTTPRequest2` インターフェイスを使用して HTTP を通じた Web 要求を作成する場合、`IXMLHTTPRequest2Callback` インターフェイスを実装して、サーバーの応答を受け取り、他のイベントに対応します。  この例では `HttpRequest` クラスを定義して Web 要求を作成し、`HttpRequestBuffersCallback` と `HttpRequestStringCallback` クラスを定義して応答を処理しています。  `HttpRequestBuffersCallback` および `HttpRequestStringCallback` クラスは `HttpRequest` クラスをサポートします。`HttpRequest` クラスはアプリケーション コードからのみ使用できます。  
  
 `HttpRequest` クラスの `GetAsync` および `PostAsync` メソッドを使うと、HTTP GET および POST のそれぞれの操作を開始することができます。  これらのメソッドは、`HttpRequestStringCallback` クラスを使用して、サーバー応答を文字列として読み取ります。  `SendAsync` と `ReadAsync` のメソッドは、大きなコンテンツをストリーム転送することができます。  これらの各メソッドは、操作を表す [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) を返します。  The `GetAsync` および `PostAsync` のメソッドは `task<std::wstring>` の値を生成し、`wstring` の部分がサーバーの応答を表します。  `SendAsync` および `ReadAsync` のメソッドは `task<void>` の値を生成します。これらのタスクは、送信と読み取り操作が完了すると、完了します。  
  
 `IXMLHTTPRequest2` インターフェイスは非同期に動作するため、この例では [concurrency::task\_completion\_event](../../parallel/concrt/reference/task-completion-event-class.md) を使用して、コールバック オブジェクトがダウンロード操作を完了するか、取り消した後に、タスクを作成します。  `HttpRequest` クラスは、このタスクからタスク ベースの継続を作成し、最終結果を設定します。  `HttpRequest` クラスは、タスク ベースの継続を使って、前のタスクがエラーを生成したり取り消された場合でも、継続タスクが実行されるようにします。  タスク ベースの継続の詳細については、「[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)」を参照してください。  
  
 取り消し操作をサポートするため、`HttpRequest`、`HttpRequestBuffersCallback`、および `HttpRequestStringCallback` のクラスは、キャンセル トークンを使用します。  `HttpRequestBuffersCallback` と `HttpRequestStringCallback` クラスは、[concurrency::cancellation\_token::register\_callback](../Topic/cancellation_token::register_callback%20Method.md) メソッドを使用して、タスクの完了イベントが取り消しに応答できるようにします。  この取り消しのコールバックは、ダウンロードを中止します。  取り消し処理の詳細については、「[キャンセル](../../parallel/concrt/cancellation-in-the-ppl.md)」を参照してください。  
  
#### HttpRequest クラスを定義するには  
  
1.  新しい XAML アプリケーション プロジェクトを作成するには、Visual C\+\+ の **\[新しいアプリケーション \(XAML\)\]** テンプレートを使用します。  この例では、プロジェクトの名前を `UsingIXMLHTTPRequest2` とします。  
  
2.  プロジェクトに HttpRequest.h という名前のヘッダー ファイルと HttpRequest.cpp という名前のソース ファイルを追加します。  
  
3.  次のコードを pch.h に追加します。  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#1](concrt-using-IXMLHTTPRequest2#1)]  
  
4.  次のコードを HttpRequest.h に追加します。  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#2](concrt-using-IXMLHTTPRequest2#2)]  
  
5.  次のコードを HttpRequest.cpp に追加します。  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#3](concrt-using-IXMLHTTPRequest2#3)]  
  
## [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで HttpRequest クラスを使用する  
 このセクションでは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリケーションで `HttpRequest` クラスを使用する方法を示します。  このアプリケーションは、URL リソースを定義する入力ボックス、GET と POST の操作を実行するボタン コマンド、現在の操作を取り消すボタン コマンドを提供します。  
  
#### HttpRequest クラスを使用するには  
  
1.  MainPage.xaml で、[StackPanel](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.stackpanel.aspx) 要素を次のように定義します。  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A1](concrt-using-IXMLHTTPRequest2#A1)]  
  
2.  MainPage.xaml.h で、この `#include` ディレクティブを追加します。  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A2](concrt-using-IXMLHTTPRequest2#A2)]  
  
3.  MainPage.xaml.h で、これらの `private` メンバー変数を `MainPage` クラスに追加します。  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A3](concrt-using-IXMLHTTPRequest2#A3)]  
  
4.  MainPage.xaml.h で `private` メソッド `ProcessHttpRequest` を宣言します。  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A4](concrt-using-IXMLHTTPRequest2#A4)]  
  
5.  MainPage.xaml.cpp で、これらの `using` ステートメントを追加します。  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A5](concrt-using-IXMLHTTPRequest2#A5)]  
  
6.  MainPage.xaml.cpp で、`MainPage` クラスの `GetButton_Click`、 `PostButton_Click`、 `CancelButton_Click` メソッドを実装します。  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A6](concrt-using-IXMLHTTPRequest2#A6)]  
  
    > [!TIP]
    >  アプリケーションが取り消しのサポートを必要としない場合は、`HttpRequest::GetAsync` と `HttpRequest::PostAsync` のメソッドに [concurrency::cancellation\_token::none](../Topic/cancellation_token::none%20Method.md) を渡します。  
  
7.  MainPage.xaml.cpp で `MainPage::ProcessHttpRequest` メソッドを実装します。  
  
     [!CODE [concrt-using-IXMLHTTPRequest2#A7](concrt-using-IXMLHTTPRequest2#A7)]  
  
8.  プロジェクトのプロパティで、**\[リンカー\]** の下の **\[入力\]** で、`shcore.lib` と `msxml6.lib`を指定します。  
  
 実行中のアプリケーションを次に示します。  
  
 ![実行中の Windows ストア アプリ](../../parallel/concrt/media/concrt_usingixhr2.png "ConcRT\_UsingIXHR2")  
  
## 次の手順  
 [同時実行ランタイムのチュートリアル](../Topic/Concurrency%20Runtime%20Walkthroughs.md)  
  
## 参照  
 [タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [キャンセル](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Asynchronous programming in C\+\+](http://msdn.microsoft.com/ja-jp/512700b7-7863-44cc-93a2-366938052f31)   
 [C\+\+ における Windows ストア アプリ用の非同期操作の作成](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)   
 [Quickstart: Connecting using XML HTTP Request \(IXMLHTTPRequest2\)](http://msdn.microsoft.com/ja-jp/cc7aed53-b2c5-4d83-b85d-cff2f5ba7b35)   
 [task クラス \(同時実行ランタイム\)](../../parallel/concrt/reference/task-class-concurrency-runtime.md)   
 [task\_completion\_event クラス](../../parallel/concrt/reference/task-completion-event-class.md)   
 [IXMLHTTPRequest2](http://msdn.microsoft.com/ja-jp/bbc11c4a-aecf-4d6d-8275-3e852e309908)   
 [IXMLHTTPRequest2Callback](http://msdn.microsoft.com/ja-jp/aa4b3f4c-6e28-458b-be25-6cce8865fc71)