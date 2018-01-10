---
title: "4.3 OMP_DYNAMIC |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 103067b28990854fb6522c19f4349a9607d65bab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="43-ompdynamic"></a>4.3 OMP_DYNAMIC
**OMP_DYNAMIC**環境変数を有効または動的に調整が明示的に有効になっているか、を呼び出すことによって無効にしない限り、並列領域を実行するために使用できるスレッドの数が動的に調整を無効になります**omp_set_dynamic**ライブラリ ルーチンです。 その値がある必要があります**TRUE**または**FALSE**です。  
  
 場合に設定**TRUE**、並列領域の実行に使用されるスレッドの数は、システム リソースを最大限に活用する、ランタイム環境で調整される可能性があります。  場合設定**FALSE**、動的に調整が無効になっています。 既定の条件では、実装定義されます。  
  
 例:  
  
```  
setenv OMP_DYNAMIC TRUE  
```  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   並列領域の詳細については、次を参照してください。[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページのです。  
  
-   **omp_set_dynamic**関数を参照してください[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)ページ 39 にします。