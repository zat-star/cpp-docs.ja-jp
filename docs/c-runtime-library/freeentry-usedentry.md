---
title: "_FREEENTRY、_USEDENTRY | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- USEDENTRY
- _USEDENTRY
- _FREEENTRY
- FREEENTRY
dev_langs:
- C++
helpviewer_keywords:
- _USEDENTRY constant
- _FREEENTRY constant
- FREEENTRY constant
- USEDENTRY constant
ms.assetid: 26f658e6-6846-4a4e-9984-262cfe392770
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 38b10c6ee985d22746633cf5cd46629456f260c8
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

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
