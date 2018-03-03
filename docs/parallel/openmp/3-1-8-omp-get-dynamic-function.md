---
title: "3.1.8 omp_get_dynamic 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd4ec73b82848efcdface781738639b05a256958
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="318-ompgetdynamic-function"></a>3.1.8 omp_get_dynamic 関数
**Omp_get_dynamic**場合は、スレッドを動的に調整が有効であり、それ以外の場合は 0 を返します関数は 0 以外の値を返します。 形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_dynamic(void);  
```  
  
 実装がスレッドの数を動的に調整を実装していない場合、この関数は常に 0 を返します。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   動的なスレッド調整については、次を参照してください。[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)ページ 39 にします。