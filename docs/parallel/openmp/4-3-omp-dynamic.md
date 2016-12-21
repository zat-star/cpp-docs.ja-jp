---
title: "4.3 OMP_DYNAMIC | Microsoft Docs"
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
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4.3 OMP_DYNAMIC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**OMP\_DYNAMIC** の環境変数が動的に調整 **omp\_set\_dynamic** ライブラリ ルーチンを呼び出して明示的に有効にするか無効か並列領域の実行に使用できるスレッドの数の動的調整を有効または無効にします。  この値は **True** または **False** である必要があります。  
  
 **True** に設定するとランタイム環境によって並列領域を実行するために使用するスレッドの数を調整することはシステム リソースを使用します。  **False** に設定して動的変更が無効になります。  既定の状態は実装定義されます。  
  
 例:  
  
```  
setenv OMP_DYNAMIC TRUE  
```  
  
## cref:  
  
-   並列領域の詳細についてはページの 8. [セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) を参照してください。  
  
-   **omp\_set\_dynamic** の関数はページの 39 [セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) が表示されます。