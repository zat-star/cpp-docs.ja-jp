---
title: "ファイルのアクセス許可定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _S_IWRITE
- _S_IREAD
dev_langs: C++
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aa42ebf645c737ffe2f5db9647a3ba3912669b27
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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