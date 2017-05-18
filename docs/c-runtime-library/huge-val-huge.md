---
title: "HUGE_VAL、_HUGE | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _HUGE
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _HUGE
- HUGE_VAL
dev_langs:
- C++
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 4c70ea331902ac16e99fcfa214af512f780829d8
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="hugeval-huge"></a>HUGE_VAL, _HUGE
## <a name="syntax"></a>構文  
  
```  
  
#include <math.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 `HUGE_VAL`表現可能な最大の double 値です。 エラーが発生した場合に、多くのランタイム数値演算関数でこの値が返されます。 一部の関数について -`HUGE_VAL` が返されます。 `HUGE_VAL` は `_HUGE` と定義されますが、ランタイム数値演算関数は `HUGE_VAL` を返します。 一貫性を保つのため、コードでも `HUGE_VAL` を使用する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [グローバル定数](../c-runtime-library/global-constants.md)
