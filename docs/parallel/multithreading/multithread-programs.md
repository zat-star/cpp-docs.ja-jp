---
title: "マルチスレッド プログラム | Microsoft Docs"
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
  - "マルチスレッド処理 [C++], スレッドの概要"
  - "スレッド処理 [C++], スレッド処理の概要"
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# マルチスレッド プログラム
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スレッドとは、プログラムを通じて実行される処理の単位です。  また、Win32 がスケジュールする実行の最小単位でもあります。  スレッドは、スタック、CPU レジスタの状態、およびシステム スケジューラの実行リストのエントリで構成されています。  各スレッドは、プロセスのすべてのリソースを共有します。  
  
 プロセスは、1 つ以上のスレッドと、メモリ上にあるプログラムのコード、データなどのリソースから構成されます。  代表的なプログラム リソースは、オープンされているファイル、セマフォ、動的に割り当てられたメモリなどです。  システム スケジューラがスレッドの 1 つに実行制御を渡すと、プログラムが実行されます。  実行させるスレッドおよびその実行時期は、スケジューラが決定します。  優先順位の低いスレッドは、優先順位の高いスレッドが完了するまで待機します。  マルチプロセッサ コンピューターでは、スケジューラは、各スレッドを別のプロセッサに移して CPU のロードを分散できます。  
  
 プロセスの中のそれぞれのスレッドは独立して動作します。  スレッドを相互に公開しない限り、スレッドは個別に実行されて、プロセスのほかのスレッドに影響されません。  ただし、共通のリソースを共有するスレッドは、セマフォなどのプロセス間通信を行って互いに処理を調整する必要があります。  スレッドの同期方法の詳細については、「[マルチスレッド Win32 プログラムの作成](../Topic/Writing%20a%20Multithreaded%20Win32%20Program.md)」を参照してください。  
  
## 参照  
 [C と Win32 を使用するマルチスレッド](../../parallel/multithreading-with-c-and-win32.md)