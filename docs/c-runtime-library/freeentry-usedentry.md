---
title: "_FREEENTRY、_USEDENTRY | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- USEDENTRY
- _USEDENTRY
- _FREEENTRY
- FREEENTRY
dev_langs: C++
helpviewer_keywords:
- _USEDENTRY constant
- _FREEENTRY constant
- FREEENTRY constant
- USEDENTRY constant
ms.assetid: 26f658e6-6846-4a4e-9984-262cfe392770
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ad8cb2b22e0de5d2067da19858a7fff290625fa0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="freeentry-usedentry"></a>_FREEENTRY、_USEDENTRY
## <a name="syntax"></a>構文  
  
```  
#include <malloc.h>  
```  
  
## <a name="remarks"></a>コメント  
 これらの定数は、`_heapwalk` ルーチンから **_HEAPINFO** 構造体の **_useflag** 要素に割り当てられた値を表します。 これらはヒープ エントリの状態を示します。  
  
## <a name="see-also"></a>関連項目  
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)