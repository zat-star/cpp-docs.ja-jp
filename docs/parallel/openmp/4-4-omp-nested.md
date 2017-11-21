---
title: "4.4 OMP_NESTED |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fbb45bb04db612451c7d081f3a7afad8031da643
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED
`OMP_NESTED`環境変数を有効または入れ子になった並列処理が有効になっている、または呼び出すことによって無効になっている場合を除き、入れ子になった並列処理を無効になります、 `o` **mp_set_nested**ライブラリ ルーチンです。 場合に設定**TRUE**、入れ子になった並列処理が有効である場合に設定されている**FALSE**、入れ子になった並列処理が無効になっています。 既定値は**FALSE**です。  
  
 例:  
  
```  
setenv OMP_NESTED TRUE  
```  
  
## <a name="cross-reference"></a>クロス リファレンス  
  
-   `omp_set_nested`関数を参照してください[セクション 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 ページのです。