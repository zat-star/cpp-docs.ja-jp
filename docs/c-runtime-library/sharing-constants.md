---
title: "共有モード定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SH_DENYNO
- _SH_DENYRD
- _SH_DENYRW
- _SH_DENYWR
- _SH_COMPAT
dev_langs:
- C++
helpviewer_keywords:
- _SH_DENYRW constant
- SH_DENYRD constant
- _SH_COMPAT constant
- _SH_DENYRD constant
- SH_DENYRW constant
- sharing constants
- SH_DENYNO constant
- _SH_DENYWR constant
- SH_DENYWR constant
- _SH_DENYNO constant
- SH_COMPAT constant
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 635c6eee50f5d1dfb19f0c1b823dab018922c490
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="sharing-constants"></a>共有モード定数
ファイル共有モードの定数。  
  
## <a name="syntax"></a>構文  
  
```  
  
#include <share.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 *shflag* 引数で、1 つまたは複数のマニフェスト定数で構成される共有モードを決定します。 これらは、*oflag* 引数と組み合わせて使用できます (「[ファイル定数](../c-runtime-library/file-constants.md)」をご覧ください)。  
  
 次の表に、定数とそれぞれの意味を示します。  
  
|定数|説明|  
|--------------|-------------|  
|`_SH_DENYRW`|ファイルへの読み取りおよび書き込みアクセスを拒否|  
|`_SH_DENYWR`|ファイルへの書き込みアクセスを拒否|  
|`_SH_DENYRD`|ファイルへの読み取りアクセスを拒否|  
|`_SH_DENYNO`|読み取りおよび書き込みアクセスを許可|  
|`_SH_SECURE`|セキュリティで保護されたモードを設定 (共有読み取り、排他的な書き込みアクセス)。|  
  
## <a name="see-also"></a>参照  
 [_sopen、_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_fsopen、_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)