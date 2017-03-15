---
title: "WinInet の基礎 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnStatusCallback メソッド"
  - "WinInet クラス, WinInet クラスの概要"
  - "WinInet クラス, 表示 (進行状況を)"
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# WinInet の基礎
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アプリケーションからファイルをダウンロードおよびアップロードするのに FTP サポートを追加するために WinInet を使用できます。  を検索し、そのファイルをダウンロードするときに [OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md) をオーバーライドし、その進行状況に関する情報を提供するために `dwContext` パラメーターを使用できます。  
  
 ここでは、次のトピックについて説明します。:  
  
-   [単純なブラウザーを作成します。](#_core_create_a_very_simple_browser)  
  
-   [Web ページをダウンロードします。](#_core_download_a_web_page)  
  
-   [FTP ファイル](#_core_ftp_a_file)  
  
-   [gopher のディレクトリを取得してください。](#_core_retrieve_a_gopher_directory)  
  
-   [転送がファイル中は、進行状況に関する情報を表示します。](#_core_display_progress_information_while_transferring_files)  
  
 コード例の抜粋を次に単純なブラウザーの作成方法について gopher ファイル Web ページ、FTP、ファイル検索をダウンロードします。  これらは、完成したコード例が示すとおりされず、すべてが例外処理は含まれません。  
  
 WinInet の詳細については、「[Win32 インターネット拡張機能 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)」を参照してください。  
  
##  <a name="_core_create_a_very_simple_browser"></a> 単純なブラウザーを作成します。  
 [!CODE [NVC_MFCWinInet#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCWinInet#1)]  
  
##  <a name="_core_download_a_web_page"></a> Web ページをダウンロードします。  
 [!CODE [NVC_MFCWinInet#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCWinInet#2)]  
  
##  <a name="_core_ftp_a_file"></a> FTP ファイル  
 [!CODE [NVC_MFCWinInet#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCWinInet#3)]  
  
##  <a name="_core_retrieve_a_gopher_directory"></a> gopher のディレクトリを取得してください。  
 [!CODE [NVC_MFCWinInet#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCWinInet#4)]  
  
## OnStatusCallback を使用します。  
 WinInet を使用することを使用すると、ステータス情報を取得するには、アプリケーションの [CInternetSession](../Topic/CInternetSession%20Class.md) オブジェクトの [OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md) のメンバーを使用します。  `CInternetSession` 独自のオブジェクトを派生し、`OnStatusCallback`をオーバーライドし、状態のコールバックを有効にした場合、MFC は、インターネット セッションのすべてのアクティビティの進行状況に関する情報を含む `OnStatusCallback` 関数を呼び出します。  
  
 単一のセッションがさまざまな別のアクションを実行する可能性のある複数の接続 \(有効期間にサポートする可能性があるため、`OnStatusCallback` は機能が特定の接続またはトランザクションの各状態の変更を特定する必要があります。  機能は、WinInet サポートのメンバー関数の多くは、指定されたコンテキスト ID パラメーターで指定されているクラスをクリックします。  このパラメーターの型 `DWORD` 常に、`dwContext`という名前です。  
  
 特定のインターネット オブジェクトに割り当てられているコンテキストがアクティビティを識別するために `CInternetSession` オブジェクトの `OnStatusCallback` のメンバー オブジェクトによって使用されます。  `OnStatusCallback` の呼び出しは、複数のパラメーターを受け取る; これらのパラメーターは、トランザクションと接続、進行状況が行われたかをアプリケーションに通知するように連携します。  
  
 `CInternetSession` オブジェクトを作成すると、コンストラクターに `dwContext` パラメーターを指定できます。  `CInternetSession` 自体はコンテキスト ID を使用して; 代わりに、**InternetConnection**\-明示的に独自のコンテキスト ID を受け付けない派生オブジェクトがコンテキスト ID を渡します。  次に、`CInternetConnection` それらのオブジェクトを作成する `CInternetFile` オブジェクトに明示的に異なるコンテキスト ID を指定するコンテキスト ID を渡します。  一方、独自の特定のコンテキスト ID、オブジェクトを指定し、作業をそのコンテキスト ID に関連付けられている  どのようなステータス情報を `OnStatusCallback` 関数の、指定されたかを識別するのにコンテキスト ID を使用できます。  
  
##  <a name="_core_display_progress_information_while_transferring_files"></a> 転送がファイル中は、進行状況に関する情報を表示します。  
 たとえば、ファイルを読み取るために FTP サーバーとの接続を作成し、HTTP サーバーに Web ページを取得するために接続するアプリケーションを作成する場合 `CInternetSession` オブジェクト、`CInternetConnection` の 2 つがオブジェクト \(1 は **CFtpSession** で他方が **CHttpSession**です\)、および `CInternetFile` の 2 つがオブジェクト \(各接続に対して 1\) があります。  `dwContext` パラメーターに既定値を使用している場合は、HTTP 接続の進行状況を示す呼び出しとが FTP 接続の進行状況を示す `OnStatusCallback` の呼び出しを区別できません。  ユーザーが `OnStatusCallback`に後にテストを実行できる `dwContext` ID の場合、操作がコールバックを生成したかを確認します。  
  
## 参照  
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)   
 [Win32 インターネット拡張機能 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)