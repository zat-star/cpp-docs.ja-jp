---
title: "旧形式のコードのためのマルチスレッド サポート (Visual C++) | Microsoft Docs"
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
  - "同時実行のプログラミング [C++]"
  - "複数の同時実行スレッド "
  - "複数のスレッド"
  - "マルチスレッド処理 [C++]"
  - "マルチスレッド処理 [C++], マルチスレッド処理の概要"
  - "プログラミング [C++], マルチスレッド"
  - "スレッド処理 [C++]"
ms.assetid: 24425b1f-5031-4c6b-aac7-017115a40e7c
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 旧形式のコードのためのマルチスレッド サポート (Visual C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ では、並列に実行する複数のスレッドを同時に実行させることができます。  マルチスレッドを使うと、バックグラウンドのタスクを別に分けたり、複数の入力ストリームを同時に管理したり、ユーザー インターフェイスを管理したりできます。  
  
## このセクションの内容  
 [C と Win32 を使用するマルチスレッド](../../parallel/multithreading-with-c-and-win32.md)  
 Microsoft Windows で動作するマルチスレッド アプリケーションの作成方法について説明します。  
  
 [C\+\+ と MFC を使用するマルチスレッド](../../parallel/multithreading-with-cpp-and-mfc.md)  
 プロセスとスレッドについて説明します。また、MFC でマルチスレッドを使用する方法についても説明します。  
  
 [マルチスレッドとロケール](../../parallel/multithreading-and-locales.md)  
 マルチスレッド アプリケーションで C ランタイム ライブラリと標準 C\+\+ ライブラリ両方のロケール機能を使用した場合に発生する問題について説明します。  
  
## 関連項目  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
 アプリケーション内の実行中のスレッドを表します。  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
 Win32 の同期オブジェクトに共通の機能を提供する純粋仮想クラスについて説明します。  
  
 [CSemaphore](../../mfc/reference/csemaphore-class.md)  
 セマフォを表します。これは、1 つ以上のプロセスの限られた数のスレッドだけがリソースにアクセスできるようにする同期オブジェクトです。  
  
 [CMutex](../../mfc/reference/cmutex-class.md)  
 ミューテックスを表します。これは、1 つのスレッドがリソースに排他アクセスできるようにする同期オブジェクトです。  
  
 [CCriticalSection](../Topic/CCriticalSection%20Class.md)  
 クリティカル セクションを表します。これは、一度に 1 つのスレッドだけがリソースまたはコード セクションにアクセスできるようにする同期オブジェクトです。  
  
 [CEvent](../../mfc/reference/cevent-class.md)  
 イベントを表します。これは、イベントが発生したことを、あるスレッドが別のスレッドに通知できるようにする同期オブジェクトです。  
  
 [CMultiLock](../../mfc/reference/cmultilock-class.md)  
 マルチスレッド プログラムで複数のリソースのアクセス制御に使うアクセス コントロール機構を表します。  
  
 [CSingleLock](../../mfc/reference/csinglelock-class.md)  
 マルチスレッド プログラムで 1 つのリソースのアクセス制御に使うアクセス コントロール機構を表します。  
  
 [\(NOTINBUILD\)Visual C\+\+ Programming Methodologies](http://msdn.microsoft.com/ja-jp/0822f806-fa81-4b65-bf0f-1e2921f30c95)  
 Visual C\+\+ ライブラリに関する概念を説明するトピックや、さまざまなコーディングの技術や技法について説明するトピックへのリンクがあります。