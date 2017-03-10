---
title: "ファイルのアクセス許可定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _S_IWRITE
- _S_IREAD
dev_langs:
- C++
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: a54b34ed093e5fc13461df58725d79a53aa31134
ms.lasthandoff: 02/24/2017

---
# <a name="file-permission-constants"></a>ファイルのアクセス許可定数
## <a name="syntax"></a>構文  
  
```  
  
#include <sys/stat.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 `_O_CREAT` (`_open`, `_sopen`) が指定されるとき、これらの定数のいずれかが必須になります。  
  
 `pmode` 引数は、次のようにファイルのアクセス許可設定を指定します。  
  
|定数|説明|  
|--------------|-------------|  
|`_S_IREAD`|読み取りが許可されます|  
|`_S_IWRITE`|書き込みが許可されます|  
|`_S_IREAD` &#124; `_S_IWRITE`|読み取りと書き込みが許可されます|  
  
 `_umask` の `pmode` 引数として使用されるとき、マニフェスト定数はアクセス許可を次のように設定します。  
  
|定数|説明|  
|--------------|-------------|  
|`_S_IREAD`|書き込み禁止 (ファイルは読み取り専用)|  
|`_S_IWRITE`|読み取り禁止 (ファイルは書き込み専用)|  
|`_S_IREAD` &#124; `_S_IWRITE`|読み取りも書き込みも禁止|  
  
## <a name="see-also"></a>関連項目  
 [_open、_wopen](../c-runtime-library/reference/open-wopen.md)   
 [_sopen、_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_umask](../c-runtime-library/reference/umask.md)   
 [標準の型](../c-runtime-library/standard-types.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)
