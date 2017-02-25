---
title: "OpenMP Directives | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 0562c263-344c-466d-843e-de830d918940
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OpenMP Directives
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

OpenMP API で使用されるディレクティブへのリンクを示します。  
  
 Visual C\+\+ ではOpenMP のディレクティブをサポートします :  
  
|ディレクティブ|Description|  
|-------------|-----------------|  
|[atomic](../../../parallel/openmp/reference/atomic.md)|とをアトミックに更新されるメモリ位置指定します。|  
|[barrier](../../../parallel/openmp/reference/barrier.md)|チームでスレッドを同期します ; すべてのスレッドがバリアにすべてのスレッドがバリアを実行するまで一時停止します。|  
|[critical](../../../parallel/openmp/reference/critical.md)|コードが 1 台のスレッドは一度に実行されることを指定します。|  
|[flush](../../../parallel/openmp/reference/flush-openmp.md)|すべてのスレッドにすべての共有オブジェクトのメモリ内の同じビューを持つことを指定します。|  
|[for](../Topic/for%20\(OpenMP\).md)|実行されるスレッドに分割できます。並列領域の内部にループでの作業になります。|  
|[master](../../../parallel/openmp/reference/master.md)|マスターの threadshould だけプログラムのセクションを実行することを指定します。|  
|[ordered](../../../parallel/openmp/reference/ordered-openmp-directives.md)|FOR ループを並列化して中のコードでは順次ループとして実行することを指定します。|  
|[parallel](../../../parallel/openmp/reference/parallel.md)|複数のスレッドで同時に実行されるコードである並列領域を定義します。|  
|[sections](../../../parallel/openmp/reference/sections-openmp.md)|すべてのスレッドに分割できます。コード例を示します。|  
|[single](../Topic/single.md)|マスター スレッド コードのセクションをシングル スレッドで実行することを指定できるようにします。|  
|[threadprivate](../Topic/threadprivate.md)|変数がスレッドに対してプライベートであることを指定します。|  
  
## 参照  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)