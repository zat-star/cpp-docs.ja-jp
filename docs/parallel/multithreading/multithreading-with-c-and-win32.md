---
title: "C と Win32 を使用するマルチスレッド | Microsoft Docs"
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
  - "マルチスレッド処理 [C++], C と Win32"
  - "スレッド処理 [C]"
  - "スレッド処理 [C++], C と Win32"
  - "Visual C, マルチスレッド"
  - "Win32 [C++], マルチスレッド"
  - "Win32 アプリケーション [C++], マルチスレッド"
  - "Windows API [C++], マルチスレッド"
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C と Win32 を使用するマルチスレッド
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft Visual C\+\+ では、Windows XP、Windows 2000、Windows NT、Windows Me、Windows 98 などの Microsoft Windows 用のマルチスレッド アプリケーションを作成できます。  アプリケーションでキーボードとマウスの同時入力などの複数の処理を管理する場合は、複数のスレッド \(マルチスレッド\) の使用を検討してください。  たとえば、あるスレッドがマウス関連の処理をしている間に、別のスレッドでキーボード入力を処理できます。  さらに 3 番目のスレッドで、マウス スレッドとキーボード スレッドからのデータに基づいて表示画面を更新することもできます。  また別のスレッドで、同時にディスク ファイルにアクセスしたり、通信 \(COM\) ポートからデータを受信することもできます。  
  
 Visual C\+\+ では、複数のスレッドを含むプログラムを作成する方法として、MFC \(Microsoft Foundation Class\) ライブラリを使用する方法と、C ランタイム ライブラリと Win32 API を使用する方法の 2 つがあります。  MFC でマルチスレッド アプリケーションを作成する方法については、C を使用するマルチスレッドに関する次のトピックを読んだ後、「[C\+\+ と MFC を使用するマルチスレッド](../../parallel/multithreading-with-cpp-and-mfc.md)」を参照してください。  
  
 以下のトピックでは、マルチスレッド プログラムの作成をサポートする Visual C\+\+ の機能について説明します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [マルチスレッド プログラム](../../parallel/multithread-programs.md)  
  
-   [ライブラリのマルチスレッド サポート](../../parallel/library-support-for-multithreading.md)  
  
-   [マルチスレッドのためのインクルード ファイル](../../parallel/include-files-for-multithreading.md)  
  
-   [スレッド コントロールのための C ランタイム ライブラリ関数](../../parallel/c-run-time-library-functions-for-thread-control.md)  
  
-   [マルチスレッドの C サンプル プログラム](../../parallel/sample-multithread-c-program.md)  
  
-   [マルチスレッド Win32 プログラムの作成](../Topic/Writing%20a%20Multithreaded%20Win32%20Program.md)  
  
-   [マルチスレッド プログラムのコンパイルとリンク](../../parallel/compiling-and-linking-multithread-programs.md)  
  
-   [マルチスレッド プログラムの問題を回避する方法](../Topic/Avoiding%20Problem%20Areas%20with%20Multithread%20Programs.md)  
  
-   [スレッド ローカル ストレージ \(TLS: Thread Local Storage\)](../../parallel/thread-local-storage-tls.md)  
  
## 参照  
 [旧形式のコードのためのマルチスレッド サポート \(Visual C\+\+\)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)