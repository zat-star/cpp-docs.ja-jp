---
title: "マルチスレッド: スレッドの終了 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CREATE_SUSPENDED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxEndThread メソッド"
  - "マルチスレッド処理 [C++], 終了 (スレッドを)"
  - "スレッドの中断"
  - "開始 (スレッドを)"
  - "停止 (スレッドを)"
  - "終了 (スレッドを)"
  - "スレッド処理 [C++], 停止 (スレッドを)"
  - "スレッド処理 [MFC], 終了 (スレッドを)"
ms.assetid: 4c0a8c6d-c02f-456d-bd02-0a8c8d006ecb
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# マルチスレッド: スレッドの終了
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

通常、スレッドは、次の 2 つの条件で終了します。1 つは制御関数が終了した場合、もう 1 つはスレッドを最後まで実行できなかった場合です。  ワード プロセッサでバックグラウンド印刷用のスレッドを使っている場合、印刷が正常に終了すると、制御関数が正常に終了します。  ただし、ユーザーが印刷をキャンセルするときは、バッググラウンド印刷用のスレッドを途中で終了する必要があります。  このトピックでは、この 2 つの終了処理を実現する方法と、スレッド終了時の終了コードを取得する方法について説明します。  
  
-   [スレッドの正常終了](#_core_normal_thread_termination)  
  
-   [スレッドの中断](#_core_premature_thread_termination)  
  
-   [スレッドの終了コードの取得](#_core_retrieving_the_exit_code_of_a_thread)  
  
##  <a name="_core_normal_thread_termination"></a> スレッドの正常終了  
 ワーカー スレッドでは、スレッドの正常終了は単純です。制御関数を終了し、終了理由を呼び出し元に返すだけです。  これには、[AfxEndThread](../Topic/AfxEndThread.md) 関数を使うことも、`return` ステートメントを使うこともできます。  通常、0 を返して正常終了を通知しますが、返す値はプログラマが決めることができます。  
  
 ユーザー インターフェイス スレッドの場合も、そのプロセスは同じように簡単です。ユーザー インターフェイス スレッド内から、[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] の [PostQuitMessage](http://msdn.microsoft.com/library/windows/desktop/ms644945) を呼び出します。  **PostQuitMessage** が取るパラメーターは、スレッドの終了コードだけです。  ワーカー スレッドの場合と同じように、通常は 0 を返して正常終了を通知します。  
  
##  <a name="_core_premature_thread_termination"></a> スレッドの中断  
 スレッドの中断もほとんど同じように単純です。終了するスレッドから [AfxEndThread](../Topic/AfxEndThread.md) を呼び出すだけです。  パラメーターは終了コードだけです。  この関数はスレッドの実行を停止し、スレッドが占有していたスタック領域を解放し、スレッドにアタッチしているすべての DLL をデタッチし、メモリからスレッド オブジェクトを削除します。  
  
 関数 `AfxEndThread` は終了するスレッドから呼び出します。  あるスレッドを別のスレッドから終了させるには、2 つのスレッド間の通信メソッドを設定する必要があります。  
  
##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a> スレッドの終了コードの取得  
 スレッドの終了コードを取得するには、ワーカー スレッドの場合も、ユーザー インターフェイス スレッドの場合も、[GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190) 関数を呼び出します  この関数については、[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] を参照してください。  この関数は、`CWinThread` オブジェクトの `m_hThread` データ メンバーに格納されている、スレッドへのハンドルと、`DWORD` のアドレスを取ります。  
  
 スレッドがまだアクティブな場合、**GetExitCodeThread** は、渡された `DWORD` 型のアドレスで **STILL\_ACTIVE** を返します。それ以外の場合は、このアドレスで終了コードを返します。  
  
 [CWinThread](../mfc/reference/cwinthread-class.md) オブジェクトの終了コードを取得するには、さらに操作が必要です。  既定では、`CWinThread` スレッドが終了すると、このスレッド オブジェクトが削除されます。  つまり、`CWinThread` オブジェクトがもう存在しないので、`m_hThread` データ メンバーにはアクセスできません。  この状況を回避するには、以下のいずれかの操作を実行します。  
  
-   `m_bAutoDelete` データ メンバーに **FALSE** を設定します。  これにより、`CWinThread` オブジェクトは、スレッドが終了した後も残ります。  次に、スレッドが終了した後で、`m_hThread` データ メンバーにアクセスできます。  ただし、この方法を使用すると、フレームワークでは `CWinThread` オブジェクトが自動的に削除されないため、このオブジェクトを直接破棄する必要があります。  この方法をお勧めします。  
  
-   スレッドへのハンドルを別に保存します。  スレッドの作成後、この `m_hThread` データ メンバーを **::DuplicateHandle** で別の変数にコピーし、この変数を通じてデータ メンバーにアクセスします。  この方法では、スレッドの終了時にオブジェクトが自動的に削除され、スレッドが終了した理由もわかります。  この場合、スレッドを終了しないと、ハンドルを複製できません。  最も安全な方法は、[AfxBeginThread](../Topic/AfxBeginThread.md) に **CREATE\_SUSPENDED** を渡してスレッドを停止状態にし、ハンドルを格納してから、[ResumeThread](../Topic/CWinThread::ResumeThread.md) を呼び出してスレッドを再開します。  
  
 この方法のどちらかを使うと、`CWinThread` オブジェクトの終了理由を判定できます。  
  
## 参照  
 [C\+\+ と MFC を使用するマルチスレッド](../parallel/multithreading-with-cpp-and-mfc.md)   
 [\_endthread、\_endthreadex](../Topic/_endthread,%20_endthreadex.md)   
 [\_beginthread、\_beginthreadex](../Topic/_beginthread,%20_beginthreadex.md)   
 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659)