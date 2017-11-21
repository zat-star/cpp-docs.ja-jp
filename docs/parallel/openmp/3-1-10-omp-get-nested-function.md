---
title: "3.1.10 omp_get_nested 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0447fd872a44d2c1eefb751e501eba4df5ec8b8f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="3110-ompgetnested-function"></a>3.1.10 omp_get_nested 関数
`omp_get_nested`関数 0 を返します入れ子になった並列処理が有効になっている場合は 0 以外の値が無効な場合です。 入れ子になった並列処理の詳細については、40 ページの 3.1.9 セクションを参照してください。 形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 実装が入れ子になった並列処理を実装していない場合、この関数は常に 0 を返します。