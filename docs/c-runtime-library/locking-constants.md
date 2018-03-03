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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4231235fc35a8b6d22f49e2ba05db337a619713
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
 指定したバイトをロック解除します。 (バイトはすでにロックされている必要があります)。  
  
## <a name="see-also"></a>参照  
 [_locking](../c-runtime-library/reference/locking.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)