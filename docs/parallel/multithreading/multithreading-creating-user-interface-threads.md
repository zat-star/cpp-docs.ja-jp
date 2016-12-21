---
title: "マルチスレッド: ユーザー インターフェイス スレッドの生成 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CREATE_SUSPENDED"
  - "SECURITY_ATTRIBUTES"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "マルチスレッド処理 [C++], ユーザー インターフェイス スレッド"
  - "スレッド処理 [C++], 作成 (スレッドを)"
  - "スレッド処理 [C++], ユーザー インターフェイス スレッド"
  - "スレッド処理 [MFC], ユーザー インターフェイス スレッド"
  - "ユーザー インターフェイス スレッド [C++]"
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# マルチスレッド: ユーザー インターフェイス スレッドの生成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ユーザー インターフェイス スレッドでは、主にユーザー入力を処理し、ユーザーが生成したイベントに応答します。この処理は、アプリケーションのほかの部分を実行しているスレッドとは無関係に行われます。  `CWinApp` の派生クラスで提供されるメイン アプリケーション スレッドは、既に生成され実行を開始しています。  このトピックでは、ユーザー インターフェイス スレッドを作成するための手順について説明します。  
  
 まず、ユーザー インターフェイス スレッド用のクラスを [CWinThread](../../mfc/reference/cwinthread-class.md) から派生します。  このクラスは [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md) マクロと [IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md) マクロを使って宣言し、実装します。  このクラスでは、一部の関数をオーバーライドする必要があります。また、他の関数も必要に応じてオーバーライドできます。  次の表に、各関数とその用途を示します。  
  
### ユーザー インターフェイス スレッドを作成するためにオーバーライドする関数  
  
|関数|目的|  
|--------|--------|  
|[ExitInstance](../Topic/CWinThread::ExitInstance.md)|スレッド終了時の後処理を行います。  通常、オーバーライドします。|  
|[InitInstance](../Topic/CWinThread::InitInstance.md)|スレッドのインスタンスを初期化します。  必ずオーバーライドします。|  
|[OnIdle](../Topic/CWinThread::OnIdle.md)|スレッド固有のアイドル処理ハンドラーを行います。  通常、オーバーライドしません。|  
|[PreTranslateMessage](../Topic/CWinThread::PreTranslateMessage.md)|メッセージを **TranslateMessage** と **DispatchMessage** に送る前にフィルタリングします。  通常、オーバーライドしません。|  
|[ProcessWndProcException](../Topic/CWinThread::ProcessWndProcException.md)|スレッドのメッセージ ハンドラーおよびコマンド ハンドラーがスローした未処理例外を受け取ります。  通常、オーバーライドしません。|  
|[&#91;実行&#93;](../Topic/CWinThread::Run.md)|スレッドの制御関数です。  メッセージ ポンプが含まれます。  この関数をオーバーライドすることはほとんどありません。|  
  
 MFC は、パラメーターのオーバーロードによって `AfxBeginThread` の 2 つのバージョンを提供します。1 つはワーカー スレッドのみを作成でき、もう 1 つは、ユーザー インターフェイス スレッドまたはワーカー スレッドを作成できます。  ユーザー インターフェイス スレッドを起動するには、[AfxBeginThread](../Topic/AfxBeginThread.md) の 2 番目のオーバーロードを呼び出して、以下のパラメーターをこの順で渡します。  
  
-   `CWinThread` の派生クラスのオブジェクトの [RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md)。  
  
-   \(省略可\) 目的の優先順位。  既定の優先順位は normal です。  優先順位の詳細については、[!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] の「[SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277)」を参照してください。  
  
-   \(省略可\) スレッドのスタック サイズ。  既定値は、このスレッドを生成するスレッドのスタックと同じサイズです。  
  
-   \(省略可\) スレッドを作成するときに一時停止状態にするには **CREATE\_SUSPENDED** を渡します。  既定値 0 では、スレッドを通常どおり起動します。  
  
-   \(省略可\) セキュリティ属性。  既定では親スレッドと同じ値になります。  このセキュリティ情報の形式の詳細については、[!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] の「[SECURITY\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)」を参照してください。  
  
 `AfxBeginThread` は、スレッド生成処理の大部分を自動的に行います。  この関数は指定されたクラスのオブジェクトを生成し、パラメーターで指定されたとおりに初期化してから、[CWinThread::CreateThread](../Topic/CWinThread::CreateThread.md) を呼び出してスレッドの実行を開始します。  なんらかの原因でスレッド生成に失敗すると、スレッド生成処理全体をチェックし、すべてのオブジェクトを確実に解放します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [マルチスレッド : スレッドの終了](../../parallel/multithreading-terminating-threads.md)  
  
-   [マルチスレッド : ワーカー スレッドの生成](../../parallel/multithreading-creating-worker-threads.md)  
  
-   [\<caps:sentence id\="tgt49" sentenceid\="d446961ca833a037f83b141ec4859428" class\="tgtSentence"\>Processes and Threads\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms684841)  
  
## 参照  
 [C\+\+ と MFC を使用するマルチスレッド](../../parallel/multithreading-with-cpp-and-mfc.md)