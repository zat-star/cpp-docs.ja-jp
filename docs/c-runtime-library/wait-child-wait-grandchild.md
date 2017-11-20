---
title: "_WAIT_CHILD、_WAIT_GRANDCHILD | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
dev_langs: C++
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1e5e3aa48f0184730a7860ea055d9b233b4ac708
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="waitchild-waitgrandchild"></a>_WAIT_CHILD、_WAIT_GRANDCHILD
## <a name="syntax"></a>構文  
  
```  
  
#include <process.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 `_cwait` 関数は、あらゆるプロセスで他のすべてのプロセスを待機するために使用できます (プロセス ID がわかっている場合)。 アクションの引数は、次の値のいずれかになります。  
  
|定数|説明|  
|--------------|-------------|  
|`_WAIT_CHILD`|呼び出しプロセスは、指定した新しいプロセスが終了するまで待機します。|  
|`_WAIT_GRANDCHILD`|呼び出しプロセスは、指定した新しいプロセスとその新しいプロセスによって生成されたすべてのプロセスが終了するまで待機します。|  
  
## <a name="see-also"></a>関連項目  
 [_cwait](../c-runtime-library/reference/cwait.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)