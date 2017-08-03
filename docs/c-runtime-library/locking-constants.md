---
title: "_locking 定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
dev_langs:
- C++
helpviewer_keywords:
- LK_UNLCK constant
- LK_NBRLCK constant
- _LK_NBRLCK constant
- _LK_NBLCK constant
- _LK_LOCK constant
- LK_NBLCK constant
- _LK_UNLCK constant
- LK_RLCK constant
- _LK_RLCK constant
- LK_LOCK constant
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
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
ms.openlocfilehash: 6e023de61dac5679d6c46c89b57255eef0b34c76
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="locking-constants"></a>_locking 定数
## <a name="syntax"></a>構文  
  
```  
  
#include <sys/locking.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 `_locking` 関数の呼び出しにおける *mode* 引数によって、実行されるロック操作が指定されます。  
  
 *mode* 引数は、次のマニフェスト定数のいずれかである必要があります。  
  
 `_LK_LOCK`  
 指定したバイトをロックします。 バイトをロックできない場合は、関数によって 1 秒後に再試行されます。 10 回試行した後、バイトをロックできなかった場合、関数はエラーを返します。  
  
 `_LK_RLCK`  
 `_LK_LOCK` と同じ。  
  
 `_LK_NBLCK`  
 指定したバイトをロックします。 バイトをロックできない場合、関数はエラーを返します。  
  
 `_LK_NBRLCK`  
 `_LK_NBLCK` と同じ。  
  
 `_LK_UNLCK`  
 指定したバイトのロックを解除します  (バイトはすでにロックされている必要があります)。  
  
## <a name="see-also"></a>関連項目  
 [_locking](../c-runtime-library/reference/locking.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)
