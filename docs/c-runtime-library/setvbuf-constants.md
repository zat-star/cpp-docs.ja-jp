---
title: "setvbuf 定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
dev_langs:
- C++
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
caps.latest.revision: 6
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
ms.openlocfilehash: 72597020534100f86de855db0095995e50d10f9b
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="setvbuf-constants"></a>setvbuf 定数
## <a name="syntax"></a>構文  
  
```  
  
#include <stdio.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 これらの定数は、`setvbuf` のバッファーの種類を表します。  
  
 使用可能な値は、次のマニフェスト定数によって与えられます。  
  
|定数|説明|  
|--------------|-------------|  
|`_IOFBF`|フル バッファリング: `setvbuf` の呼び出しで指定したバッファーが使用され、そのサイズは `setvbuf` の呼び出しで指定したとおりになります。 バッファー ポインターが **NULL** の場合は、指定したサイズで自動的に割り当てられたバッファーが使用されます。|  
|`_IOLBF`|`_IOFBF` と同じ。|  
|`_IONBF`|`setvbuf` 呼び出しの引数に関係なく、バッファーは使用されません。|  
  
## <a name="see-also"></a>関連項目  
 [setbuf](../c-runtime-library/reference/setbuf.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)
