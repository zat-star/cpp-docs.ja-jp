---
title: "古いコード (Visual C) のマルチ スレッド サポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [C++]
- multiple threads
- concurrent programming [C++]
- programming [C++], multithreaded
- multithreading [C++], about multithreading
- multiple concurrent threads
- multithreading [C++]
ms.assetid: 24425b1f-5031-4c6b-aac7-017115a40e7c
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1037b8b81c9286ac1b1dd9303294b4300e7c9309
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-support-for-older-code-visual-c"></a>旧形式のコードのためのマルチスレッド サポート (Visual C++)
Visual C++ では、並列に実行する複数のスレッドを同時に実行させることができます。 マルチスレッドを使うと、バックグラウンドのタスクを別に分けたり、複数の入力ストリームを同時に管理したり、ユーザー インターフェイスを管理したりできます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [C と Win32 を使用するマルチスレッド](../parallel/multithreading-with-c-and-win32.md)  
 Microsoft Windows で動作するマルチスレッド アプリケーションの作成方法について説明します。  
  
 [C++ と MFC を使用するマルチスレッド](../parallel/multithreading-with-cpp-and-mfc.md)  
 プロセスとスレッドについて説明します。また、MFC でマルチスレッドを使用する方法についても説明します。  
  
 [マルチスレッドとロケール](../parallel/multithreading-and-locales.md)  
 C ランタイム ライブラリとマルチ スレッド アプリケーションでは、C++ 標準ライブラリの両方のロケール機能を使用する場合に発生する問題について説明します。  
  
## <a name="related-sections"></a>関連項目  
 [CWinThread](../mfc/reference/cwinthread-class.md)  
 アプリケーション内の実行中のスレッドを表します。  
  
 [関数](../mfc/reference/csyncobject-class.md)  
 Win32 の同期オブジェクトに共通の機能を提供する純粋仮想クラスについて説明します。  
  
 [CSemaphore](../mfc/reference/csemaphore-class.md)  
 セマフォを表します。これは、1 つ以上のプロセスの限られた数のスレッドだけがリソースにアクセスできるようにする同期オブジェクトです。  
  
 [CMutex](../mfc/reference/cmutex-class.md)  
 ミューテックスを表します。これは、1 つのスレッドがリソースに排他アクセスできるようにする同期オブジェクトです。  
  
 [CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
 クリティカル セクションを表します。これは、一度に 1 つのスレッドだけがリソースまたはコード セクションにアクセスできるようにする同期オブジェクトです。  
  
 [CEvent](../mfc/reference/cevent-class.md)  
 イベントを表します。これは、イベントが発生したことを、あるスレッドが別のスレッドに通知できるようにする同期オブジェクトです。  
  
 [CMultiLock](../mfc/reference/cmultilock-class.md)  
 マルチスレッド プログラムで複数のリソースのアクセス制御に使うアクセス コントロール機構を表します。  
  
 [CSingleLock](../mfc/reference/csinglelock-class.md)  
 マルチスレッド プログラムで 1 つのリソースのアクセス制御に使うアクセス コントロール機構を表します。  
  
 [(NOTINBUILD)Visual C のプログラミング手法](http://msdn.microsoft.com/en-us/0822f806-fa81-4b65-bf0f-1e2921f30c95)  
 Visual C++ ライブラリに関する概念を説明するトピックや、さまざまなコーディングの技術や技法について説明するトピックへのリンクがあります。