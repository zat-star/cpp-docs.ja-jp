---
title: "EXIT_SUCCESS、EXIT_FAILURE | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- EXIT_FAILURE
- EXIT_SUCCESS
dev_langs:
- C++
helpviewer_keywords:
- EXIT_SUCCESS constant
- EXIT_FAILURE constant
ms.assetid: ff2c82cb-c0bb-4556-a812-59aa278bfac5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 232f01ffd829fa367a35193b23c6fea56e4ea4d9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exitsuccess-exitfailure"></a>EXIT_SUCCESS、EXIT_FAILURE
## <a name="syntax"></a>構文  
  
```  
  
#include <stdlib.h>  
```  
  
## <a name="remarks"></a>コメント  
 これらは **exit** 関数と `_exit` 関数の引数であり、`atexit` 関数と `_onexit` 関数の戻り値です。  
  
## <a name="see-also"></a>参照  
 [atexit](../c-runtime-library/reference/atexit.md)   
 [exit、_Exit、_exit](../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit、_onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)