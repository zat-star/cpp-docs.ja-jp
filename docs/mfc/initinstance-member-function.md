---
title: "InitInstance メンバー関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "InitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アプリケーション [MFC], 初期化"
  - "初期化 (MFC アプリケーションを)"
  - "InitInstance メソッド"
  - "MFC [C++], 初期化"
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# InitInstance メンバー関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows オペレーティング システムの同じアプリケーション内の複数のコピー、または「」、インスタンスを実行できます。  `WinMain`、アプリケーションの新しいインスタンスを起動するたびに [InitInstance](../Topic/CWinApp::InitInstance.md) を呼び出します。  
  
 MFC アプリケーション ウィザードで作成される標準の `InitInstance` の実装は、次のタスクを実行する:  
  
-   中心機能として、ドキュメント、ビュー、およびフレーム ウィンドウを作成するドキュメント テンプレートを作成します。  このプロセスの詳細については、「[ドキュメント テンプレートの作成](../Topic/Document%20Template%20Creation.md)」を参照してください。  
  
-   最近使用したファイルの名前を含む .ini ファイルまたは Windows レジストリからの読み込み標準ファイル オプション。  
  
-   一つまたは複数のドキュメント テンプレートを登録します。  
  
-   MDI アプリケーションでは、メイン フレーム ウィンドウを作成します。  
  
-   コマンド ラインをコマンド ラインで指定した文書を開くか、新しい空のドキュメントを開くために処理します。  
  
 、初期化コードを追加するか、ウィザードが作成したコードを変更できます。  
  
> [!NOTE]
>  MFC アプリケーションは、シングルスレッド アパートメント \(STA\) として初期化する必要があります。  [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) を `InitInstance` オーバーライド内で呼び出す場合は、`COINIT_APARTMENTTHREADED` を指定します \( `COINIT_MULTITHREADED` を指定しません\)。  詳細については、For more information, see PRB: MFC Application Stops Responding When You Initialize the Application as a Multithreaded Apartment \(828643\) at [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;828643](http://support.microsoft.com/default.aspx?scid=kb;en-us;828643) にある "PRB: MFC Application Stops Responding When You Initialize the Application as a Multithreaded Apartment \(828643\) \(PRB: アプリケーションをマルチスレッド アパートメントとして初期化したときに、MFC アプリケーションが応答を停止する \(828643\)\)" を参照してください。  
  
## 参照  
 [CWinApp : アプリケーション クラス](../Topic/CWinApp:%20The%20Application%20Class.md)