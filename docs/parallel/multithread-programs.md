---
title: "マルチ スレッド プログラム |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [C++], about threading
- multithreading [C++], about threads
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0ff73b4d3a1c8ee6971fbd3f88f491c2a5c76311
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="multithread-programs"></a>マルチスレッド プログラム
スレッドは、基本的には、プログラム実行のパスです。 Win32 のスケジュール実行の最小単位です。 スレッドは、スタック、CPU レジスタとシステムのスケジューラの実行のリスト内のエントリの状態で構成されます。 各スレッドは、プロセスのすべてのリソースを共有します。  
  
 プロセスは、1 つまたは複数のスレッドと、コード、データ、およびその他のリソースのメモリ内のプログラムで構成されます。 一般的なプログラム リソースは開いているファイル、セマフォ、および動的に割り当てられたメモリです。 プログラムでは、実行制御がシステム スケジューラからでは、スレッドの 1 つを実行します。 スケジューラは、どのスレッドが実行するが実行されるタイミングを決定します。 優先順位の低いスレッドは、優先度の高いスレッドは、各自のタスクを完了するまで待機する必要があります。 マルチプロセッサ コンピューターで、スケジューラは、別のプロセッサが CPU の負荷を分散する個別のスレッドを移動できます。  
  
 プロセス内の各スレッドは独立して動作します。 表示されるように互いにしない限り、スレッドは個別に実行し、プロセスの他のスレッドに対応していないです。 ただし、共通のリソースを共有するスレッドは、セマフォまたはプロセス間通信の別のメソッドを使用して、作業を調整する必要があります。 スレッドの同期の詳細については、次を参照してください。[マルチ スレッド Win32 プログラムの作成](../parallel/writing-a-multithreaded-win32-program.md)です。  
  
## <a name="see-also"></a>参照  
 [C と Win32 を使用するマルチスレッド](../parallel/multithreading-with-c-and-win32.md)