---
title: "C と Win32 を使用するマルチ スレッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows API [C++], multithreading
- multithreading [C++], C and Win32
- Visual C, multithreading
- Win32 applications [C++], multithreading
- threading [C++], C and Win32
- Win32 [C++], multithreading
- threading [C]
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 30c7833a4df80669b6223f1fe6b1ccceed0257cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-with-c-and-win32"></a>C と Win32 を使用するマルチスレッド
Microsoft Visual C は、Microsoft Windows でマルチ スレッド アプリケーションを作成するためのサポートを提供します。 Windows XP、Windows 2000、Windows NT、Windows Me、および Windows 98 です。 アプリケーションでキーボードとマウスの同時入力などの複数の処理を管理する場合は、複数のスレッド (マルチスレッド) の使用を検討してください。 たとえば、あるスレッドがマウス関連の処理をしている間に、別のスレッドでキーボード入力を処理できます。 さらに 3 番目のスレッドで、マウス スレッドとキーボード スレッドからのデータに基づいて表示画面を更新することもできます。 また別のスレッドで、同時にディスク ファイルにアクセスしたり、通信 (COM) ポートからデータを受信することもできます。  
  
 Visual C++ では、複数のスレッドを含むプログラムを作成する方法として、MFC (Microsoft Foundation Class) ライブラリを使用する方法と、C ランタイム ライブラリと Win32 API を使用する方法の 2 つがあります。 MFC でマルチ スレッド アプリケーションの作成方法の詳細については、次を参照してください[C++ と MFC を使用するマルチ スレッド](../parallel/multithreading-with-cpp-and-mfc.md)c でのマルチ スレッドに関する次のトピックを読む。  
  
 以下のトピックでは、マルチスレッド プログラムの作成をサポートする Visual C++ の機能について説明します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [どのようなマルチ スレッド処理については、](../parallel/multithread-programs.md)  
  
-   [ライブラリのサポートのマルチ スレッド](../parallel/library-support-for-multithreading.md)  
  
-   [ファイルをインクルードするマルチ スレッド](../parallel/include-files-for-multithreading.md)  
  
-   [スレッド コントロールのための C ランタイム ライブラリ関数](../parallel/c-run-time-library-functions-for-thread-control.md)  
  
-   [C のサンプルのマルチ スレッド プログラム](../parallel/sample-multithread-c-program.md)  
  
-   [マルチ スレッド Win32 プログラムの作成](../parallel/writing-a-multithreaded-win32-program.md)  
  
-   [コンパイルとリンクのマルチ スレッド プログラム](../parallel/compiling-and-linking-multithread-programs.md)  
  
-   [マルチ スレッド プログラムの問題の回避](../parallel/avoiding-problem-areas-with-multithread-programs.md)  
  
-   [スレッド ローカル ストレージ (TLS)](../parallel/thread-local-storage-tls.md)  
  
## <a name="see-also"></a>参照  
 [旧形式のコードのためのマルチスレッド サポート (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)