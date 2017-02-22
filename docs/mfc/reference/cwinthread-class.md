---
title: "CWinThread クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinThread クラス"
  - "スレッド処理 [MFC], creating threads"
  - "スレッド処理 [MFC], セーフ"
  - "ワーカー スレッド"
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CWinThread クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アプリケーション内の実行中のスレッドを表します。  
  
## 構文  
  
```  
class CWinThread : public CCmdTarget  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CWinThread::CWinThread](../Topic/CWinThread::CWinThread.md)|`CWinThread` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CWinThread::CreateThread](../Topic/CWinThread::CreateThread.md)|`CWinThread` のオブジェクトの実行を開始します。|  
|[CWinThread::ExitInstance](../Topic/CWinThread::ExitInstance.md)|、スレッドが終了時の後処理のためにオーバーライドします。|  
|[CWinThread::GetMainWnd](../Topic/CWinThread::GetMainWnd.md)|スレッドのメイン ウィンドウへのポインターを取得します。|  
|[CWinThread::GetThreadPriority](../Topic/CWinThread::GetThreadPriority.md)|現在のスレッドの優先順位を取得します。|  
|[CWinThread::InitInstance](../Topic/CWinThread::InitInstance.md)|スレッドのインスタンスの初期化のためにオーバーライドします。|  
|[CWinThread::IsIdleMessage](../Topic/CWinThread::IsIdleMessage.md)|特別なメッセージをチェックします。|  
|[CWinThread::OnIdle](../Topic/CWinThread::OnIdle.md)|スレッド固有のアイドル処理のためにオーバーライドします。|  
|[CWinThread::PostThreadMessage](../Topic/CWinThread::PostThreadMessage.md)|`CWinThread` の別のオブジェクトにメッセージをポストします。|  
|[CWinThread::PreTranslateMessage](../Topic/CWinThread::PreTranslateMessage.md)|Windows 関数の [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) や [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) にディスパッチする前にメッセージにフィルターをかけます。|  
|[CWinThread::ProcessMessageFilter](../Topic/CWinThread::ProcessMessageFilter.md)|アプリケーションに届く前に、特定のメッセージを受け取ります。|  
|[CWinThread::ProcessWndProcException](../Topic/CWinThread::ProcessWndProcException.md)|スレッドのメッセージとコマンド ハンドラーがスローしたすべての未処理の例外を受け取ります。|  
|[CWinThread::PumpMessage](../Topic/CWinThread::PumpMessage.md)|スレッドのメッセージ ループが含まれます。|  
|[CWinThread::ResumeThread](../Topic/CWinThread::ResumeThread.md)|スレッドを中断してカウントをデクリメントします。|  
|[CWinThread::Run](../Topic/CWinThread::Run.md)|メッセージ ポンプを使ってスレッドの制御関数。  既定のメッセージ ループをカスタマイズするためにオーバーライドします。|  
|[CWinThread::SetThreadPriority](../Topic/CWinThread::SetThreadPriority.md)|現在のスレッドの優先順位を設定します。|  
|[CWinThread::SuspendThread](../Topic/CWinThread::SuspendThread.md)|スレッドを中断してカウントをインクリメントします。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CWinThread::operator HANDLE](../Topic/CWinThread::operator%20HANDLE.md)|`CWinThread` のオブジェクトのハンドルを取得します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CWinThread::m\_bAutoDelete](../Topic/CWinThread::m_bAutoDelete.md)|スレッドの終了にオブジェクトを破棄するかどうかを指定します。|  
|[CWinThread::m\_hThread](../Topic/CWinThread::m_hThread.md)|現在のスレッドへのハンドル。|  
|[CWinThread::m\_nThreadID](../Topic/CWinThread::m_nThreadID.md)|現在のスレッドの ID。|  
|[CWinThread::m\_pActiveWnd](../Topic/CWinThread::m_pActiveWnd.md)|OLE サーバーが埋め込み先編集が有効な場合のコンテナー アプリケーションのメイン ウィンドウへのポインターです。|  
|[CWinThread::m\_pMainWnd](../Topic/CWinThread::m_pMainWnd.md)|アプリケーションのメイン ウィンドウへのポインターを保持します。|  
  
## 解説  
 実行のメイン スレッドは通常 `CWinApp`から派生したオブジェクトによって提供されます; `CWinApp` は `CWinThread`から派生します。  `CWinThread` の追加オブジェクトは、特定のアプリケーション内に複数のスレッドができます。  
  
 `CWinThread` がサポートするスレッドの 2 種類の一般的な種類があります: ワーカー スレッドとユーザー インターフェイス スレッド。  ワーカー スレッドにメッセージ ポンプがありません: たとえば、スプレッドシートのアプリケーションでバックグラウンド計算を実行するスレッド。  ユーザー インターフェイス スレッドにシステムから受け取ったメッセージをポンプとプロセスのメッセージがあります。  [CWinApp](../../mfc/reference/cwinapp-class.md) とその派生クラスは、ユーザー インターフェイス スレッドの例です。  ほかのユーザー インターフェイス スレッドは、`CWinThread`から直接取得できます。  
  
 クラス `CWinThread` のオブジェクトは、スレッドの期間中、通常、になります。  この動作を変更する場合 **FALSE**に [m\_bAutoDelete](../Topic/CWinThread::m_bAutoDelete.md) を設定します。  
  
 `CWinThread` のクラスは、コードと MFC スレッド セーフを完全に行う必要です。  スレッド固有の情報を保持するために、フレームワークによって使用されるスレッド ローカル データが `CWinThread` のオブジェクトによって管理されます。  このため、スレッド ローカル データを MFC で処理 `CWinThread` へのリンクは、MFC を使用するすべてのスレッド作成する必要があります。  たとえば、ランタイム関数 [\_beginthread、\_beginthreadex](../Topic/_beginthread,%20_beginthreadex.md) によって作成されるスレッドは、MFC の API を使用できません。  
  
 スレッドを作成するには、[AfxBeginThread](../Topic/AfxBeginThread.md)を呼び出します。  ワーカー スレッドまたはユーザー インターフェイスが必要かを 2 とおりの形式が異なります。  ユーザー インターフェイス スレッドを作成するときは、の `CWinThread`の `CRuntimeClass` に `AfxBeginThread` 派生クラスにポインターを渡します。  ワーカー スレッドを作成する場合は、制御関数に制御関数およびパラメーターに `AfxBeginThread` にポインターを渡します。  両方のワーカー スレッドとユーザー インターフェイス スレッドに対して、優先度、スタックのサイズは、作成フラグとセキュリティ属性を変更する省略可能なパラメーターを指定できます。  `AfxBeginThread` は `CWinThread` に、新しいオブジェクトへのポインターを返します。  
  
 `AfxBeginThread`を呼び出す代わりに、`CWinThread`の派生オブジェクトを構築し、次に `CreateThread`を呼び出すことができます。  この式は階層構造のメソッドは、スレッド実行の継続的な作成と終了時の `CWinThread` のオブジェクトを再利用する場合に便利です。  
  
 `CWinThread`の詳細については、" " [C\+\+ と MFC によるマルチスレッド](../../parallel/multithreading-with-cpp-and-mfc.md)、[マルチスレッド: ユーザー インターフェイス スレッドの作成](../../parallel/multithreading-creating-user-interface-threads.md)、[マルチスレッド: ワーカー スレッドの作成](../../parallel/multithreading-creating-worker-threads.md)と [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `CWinThread`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [CCmdTarget クラス](../Topic/CCmdTarget%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)   
 [CCmdTarget クラス](../Topic/CCmdTarget%20Class.md)