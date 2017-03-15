---
title: "3.1.7 omp_set_dynamic Function | Microsoft Docs"
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
ms.assetid: 1fba961b-b82c-4a1e-ab0f-e4be826e50ab
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.7 omp_set_dynamic Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**omp\_set\_dynamic** の関数は並列領域の実行に使用できるスレッドの数の動的調整を有効または無効にします。  形式は次のとおりです。  
  
```  
#include <omp.h>  
void omp_set_dynamic(int dynamic_threads);  
```  
  
 *dynamic\_threads が*  以外の値に評価するとその後の並列領域を実行するために使用されるスレッドの数はさまざまなランタイム環境で使用するシステム リソースを自動的に調整されることがあります。  結果としてユーザーが指定したスレッドの数は最大スレッド数です。  並列領域を実行中のチーム内のスレッドの数は並列領域の期間に固定されたまま**omp\_get\_num\_threads** の関数によって報告されます。  
  
 *dynamic\_threads が*  0 に評価された場合動的な場合は無効になります。  
  
 プログラムの部分から呼び出されたとき **omp\_in\_parallel** 関数の戻り値をこの関数は前に説明した結果になります。  これは **omp\_in\_parallel** 関数の戻り値が以外の値この関数の動作は未定義にするプログラムの部分から呼び出されます。  
  
 **omp\_set\_dynamic** の呼び出しに **OMP\_DYNAMIC** の環境変数上の方が優先されます。  
  
 スレッドを動的に調整の既定値は実装定義されます。  その結果正しい実装のスレッドの特定の数値に依存しているユーザー コードは明示的に動的なスレッドを無効にする必要があります。  実装は動的にスレッド数を調整する機能を提供する必要はありませんがすべてのプラットフォーム間の移植性をサポートするためのインターフェイスを提供する必要があります。  
  
## cref:  
  
-   **omp\_get\_num\_threads** の関数はページの 37 [セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) が表示されます。  
  
-   **OMP\_DYNAMIC** の環境変数はページの 49 [セクション 4.3](../../parallel/openmp/4-3-omp-dynamic.md) が表示されます。  
  
-   **omp\_in\_parallel** の関数はページの 38 [セクション 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) が表示されます。