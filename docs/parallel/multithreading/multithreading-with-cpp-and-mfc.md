---
title: "C++ と MFC を使用するマルチスレッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "CWinThread クラス, 目的"
  - "MFC [C++], マルチスレッド"
  - "マルチスレッド処理 [C++], MFC"
  - "同期 [C++], マルチスレッド"
  - "同期クラス [C++]"
  - "スレッド処理 [C++], MFC"
  - "スレッド処理 [MFC]"
  - "スレッド処理 [MFC], スレッド処理の概要"
  - "ユーザー インターフェイス スレッド [C++]"
  - "ワーカー スレッド [C++]"
ms.assetid: 979605f8-3988-44b5-ac9c-b8cce7fcce14
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ と MFC を使用するマルチスレッド
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC \(Microsoft Foundation Class\) ライブラリでは、マルチスレッド アプリケーションがサポートされています。  このトピックでは、プロセスとスレッドについて説明します。また、MFC でマルチスレッドを使用する方法についても説明します。  
  
 プロセスとは、現在実行されているアプリケーションのインスタンスのことです。  たとえば、\[メモ帳\] アイコンをダブルクリックすると、メモ帳のプロセスが起動されます。  
  
 スレッドとは、プロセスの中で実行される処理の単位です。  メモ帳を起動すると、オペレーティング システムは 1 個のプロセスを生成し、このプロセスのプライマリ スレッドの処理を開始します。  プライマリ スレッドが終了すると、プロセスが終了します。  このプライマリ スレッドは、スタートアップ コードから関数アドレスによってオペレーティング システムに渡されます。  通常、**main** 関数または `WinMain` 関数のアドレスが渡されます。  
  
 必要に応じて、プライマリ スレッド以外のスレッドを作成できます \(マルチスレッド\)。  新しく生成したスレッドは、ユーザーが終了を待つ必要がないバックグラウンド処理またはメンテナンス処理を行う際に使用できます。  MFC アプリケーションのスレッドはすべて [CWinThread](../../mfc/reference/cwinthread-class.md) オブジェクトとして表されます。  ほとんどの場合、`CWinThread` オブジェクトはプログラム上で直接生成する必要はありません。フレームワークの [AfxBeginThread](../Topic/AfxBeginThread.md) ヘルパー関数を呼び出すと生成されます。  
  
 MFC では、ユーザー インターフェイス スレッドとワーカー スレッドの 2 種類に区別されます。  ユーザー インターフェイス スレッドでは主に、ユーザー入力を処理し、ユーザーが生成したイベントおよびメッセージに応答します。  ワーカー スレッドでは、ユーザー入力が必要ない、再計算などの処理を行います。  Win32 API ではこの 2 つのスレッドを区別しません。スレッドの起動アドレスがわかれば、スレッドを実行できます。  MFC では、ユーザー インターフェイス上のイベントに対してメッセージ ポンプを指定することにより、ユーザー インターフェイス スレッドに対して専用の処理を行います。  `CWinApp` は、`CWinThread` から派生したユーザー インターフェイス スレッド オブジェクトの例であり、ユーザーが生成したイベントおよびメッセージを処理します。  
  
 複数のスレッドが同一のオブジェクトにアクセスする場合は注意が必要です。  このような状況で発生する問題の対処方法については、「[マルチスレッド : プログラミングのヒント](../../parallel/multithreading-programming-tips.md)」を参照してください。  「[マルチスレッド : 同期クラスの使用法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」では、複数のスレッドから単一のオブジェクトへのアクセスを同期する際に使用できるクラスについて説明します。  
  
 マルチスレッド プログラムの作成とデバッグには高度な技術が必要です。プログラマはオブジェクトが一度に複数のスレッドからアクセスされないようにする必要があるからです。  マルチスレッドに関連するトピックでは、マルチスレッド プログラムで MFC を使用する方法について説明しますが、マルチスレッド プログラミング技術の基礎については説明していません。  Visual C\+\+ に付属のマルチスレッド MFC サンプル アプリケーションでは、マルチスレッド機能の追加方法や MFC でサポートされない Win32 API を利用した例が示されていますが、これはほんの出発点です。  
  
 オペレーティング システムでプロセスとスレッドが処理されるしくみの詳細については、[!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] の「[Processes and Threads](http://msdn.microsoft.com/library/windows/desktop/ms684841)」を参照してください。  
  
 MFC がサポートするマルチスレッド機能の詳細については、次のトピックを参照してください。  
  
-   [マルチスレッド : ユーザー インターフェイス スレッドの生成](../../parallel/multithreading-creating-user-interface-threads.md)  
  
-   [マルチスレッド : ワーカー スレッドの生成](../../parallel/multithreading-creating-worker-threads.md)  
  
-   [マルチスレッド : 同期クラスの使用法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)  
  
-   [マルチスレッド : スレッドの終了](../../parallel/multithreading-terminating-threads.md)  
  
-   [マルチスレッド : プログラミングのヒント](../../parallel/multithreading-programming-tips.md)  
  
-   [マルチスレッド : 同期クラスの使い分け](../../parallel/multithreading-when-to-use-the-synchronization-classes.md)  
  
## 参照  
 [旧形式のコードのためのマルチスレッド サポート \(Visual C\+\+\)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)