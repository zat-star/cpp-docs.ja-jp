---
title: "マルチスレッド: 同期クラスの使い分け | Microsoft Docs"
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
  - "制御されたリソースへのアクセス [C++]"
  - "マルチスレッド処理 [C++], 同期クラス"
  - "リソース [C++], マルチスレッド"
  - "同期 [C++], マルチスレッド"
  - "同期アクセス クラス [C++]"
  - "同期クラス [C++]"
  - "スレッド処理 [C++], 同期"
  - "スレッド処理 [MFC], 同期クラス"
ms.assetid: 4914f54e-68ac-438f-93c9-c013455a657e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# マルチスレッド: 同期クラスの使い分け
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC に用意されているマルチスレッド クラスは 2 種類に分類できます。同期オブジェクト \([CSyncObject](../mfc/reference/csyncobject-class.md)、[CSemaphore](../mfc/reference/csemaphore-class.md)、[CMutex](../mfc/reference/cmutex-class.md)、[CCriticalSection](../Topic/CCriticalSection%20Class.md)、[CEvent](../mfc/reference/cevent-class.md)\) と同期アクセス オブジェクト \([CMultiLock](../mfc/reference/cmultilock-class.md)、[CSingleLock](../mfc/reference/csinglelock-class.md)\) です。  
  
 同期クラスは、リソースへのアクセスを制御してリソースの整合性を保証するときに使います。  同期アクセス クラスは、これらの被制御リソースにアクセスするときに使います。  このトピックでは、各クラスの使い分けについて説明します。  
  
 使用する同期クラスは、以下の質問に対する回答によって決まります。  
  
1.  アプリケーションは、なんらかの要因が発生するまで、リソースにアクセスできないですか \(通信ポートからデータを受信しないと、データをファイルに書き込めない場合など\)。  
  
     これに該当する場合は、`CEvent` を使用します。  
  
2.  同じアプリケーション内の複数のスレッドから同時にリソースにアクセスできますか \(アプリケーションで 5 つまでのウィンドウのビューに同じドキュメントを表示できる場合など\)。  
  
     これに該当する場合は、`CSemaphore` を使用します。  
  
3.  複数のアプリケーションでリソースを使用できますか \(リソースが DLL 内にある場合など\)。  
  
     これに該当する場合は、`CMutex` を使用します。  
  
     いずれにも該当しない場合は、`CCriticalSection` を使います。  
  
 **CSyncObject** は直接使わないでください。  このクラスは、ほかの 4 つの同期クラスの基本クラスです。  
  
## 例 1 : 3 種類の同期クラスを使う方法  
 たとえば、アカウントのリンク リストを保持するアプリケーションの場合を考えます。  このアプリケーションでは 3 つまでのアカウントを個別のウィンドウで調べることができます。ただし、一度に更新できるアカウントは 1 つだけとします。  更新されたデータはネットワークを通じてデータ アーカイブに送られます。  
  
 このアプリケーションでは、3 種類の同期クラスをすべて使います。  同時に調べることができるアカウントは 3 つまでなので、`CSemaphore` を使って 3 つのビュー オブジェクトだけにアクセスを制限します。  4 番目のアカウントを表示しようとすると、アプリケーションは最初の 3 つのウィンドウのいずれかが閉じるのを待つか、失敗します。  アカウントを更新する場合、アプリケーションは `CCriticalSection` を使って一度に 1 つのアカウントだけを更新します。  更新に成功すると、`CEvent` を発行し、このイベントの発行を待っていたスレッドを解放します。  新しいデータは、このスレッドからデータ アーカイブに送られます。  
  
## 例 2 : 同期アクセス クラスを使う方法  
 同期アクセス クラスを使い分けるのはさらに簡単です。  アプリケーションが単一の被制御リソースにアクセスするときは、`CSingleLock` を使います。  複数の被制御リソースのいずれかにアクセスするときは、`CMultiLock` を使います。  例 1 では、一度に 1 つのリソースが必要なので、`CSingleLock` を使用します。  
  
 同期クラスの使用方法については、「[マルチスレッド : 同期クラスの使用法](../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。  同期については、[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] の「[Synchronization](http://msdn.microsoft.com/library/windows/desktop/ms686353)」を参照してください。  MFC によるマルチスレッドのサポートについては、「[C\+\+ と MFC を使用するマルチスレッド](../parallel/multithreading-with-cpp-and-mfc.md)」を参照してください。  
  
## 参照  
 [C\+\+ と MFC を使用するマルチスレッド](../parallel/multithreading-with-cpp-and-mfc.md)