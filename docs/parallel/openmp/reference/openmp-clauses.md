---
title: "OpenMP Clauses | Microsoft Docs"
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
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Clauses
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

OpenMP API で使用される句へのリンクを示します。  
  
 Visual C\+\+ ではOpenMP の次の句をサポートします :  
  
|句|Description|  
|-------|-----------------|  
|[copyin](../Topic/copyin.md)|[threadprivate](../Topic/threadprivate.md) の変数のマスター スレッドの値にアクセスするにはスレッド。|  
|[copyprivate](../Topic/copyprivate.md)|一つ以上の変数がすべてのスレッドで共有されることを指定します。|  
|[default](../../../parallel/openmp/reference/default-openmp.md)|並列領域で unscoped 変数の動作を指定します。|  
|[firstprivate](../Topic/firstprivate.md)|前にparallel コンストラクトあるため各スレッドは変数が個別のインスタンスが必要であり変数に変数の値で初期化することを指定します。|  
|[if](../../../parallel/openmp/reference/if-openmp.md)|ループを並列でもシリアル実行するかどうかを指定します。|  
|[lastprivate](../../../parallel/openmp/reference/lastprivate.md)|どのスレッドが最後のイテレーション \(の場合\) またはループ構造の最後のセクション \(\#pragma セクション\) を実装する外側のコンテキストでは変数のバージョンがプライベート バージョンと等しい値に設定であることを指定します。|  
|[nowait](../../../parallel/openmp/reference/nowait.md)|ディレクティブで暗黙のバリアをオーバーライドします。|  
|[num\_threads](../../../parallel/openmp/reference/num-threads.md)|スレッドのスレッドの数を設定します。|  
|[ordered](../Topic/ordered%20\(OpenMP%20Clauses\).md)|[ordered](../../../parallel/openmp/reference/ordered-openmp-directives.md) のディレクティブがループで使用する場合 [for](../Topic/for%20\(OpenMP\).md) の並列ステートメントには必ず指定します。|  
|[private](../../../parallel/openmp/reference/private-openmp.md)|各スレッドは変数が個別のインスタンスが必要であることを指定します。|  
|[reduction](../../../parallel/openmp/reference/reduction.md)|各スレッドに対してプライベートである一つ以上の変数が並列領域の最後にあるリダクション演算の項目であることを指定します。|  
|[schedule](../../../parallel/openmp/reference/schedule.md)|[for](../Topic/for%20\(OpenMP\).md) にディレクティブを適用します。|  
|[shared](../../../parallel/openmp/reference/shared-openmp.md)|一つ以上の変数がすべてのスレッドで共有されることを指定します。|  
  
## 参照  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)