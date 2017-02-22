---
title: "共有モード定数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SH_DENYNO"
  - "_SH_DENYRD"
  - "_SH_DENYRW"
  - "_SH_DENYWR"
  - "_SH_COMPAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_SH_COMPAT 定数"
  - "_SH_DENYNO 定数"
  - "_SH_DENYRD 定数"
  - "_SH_DENYRW 定数"
  - "_SH_DENYWR 定数"
  - "SH_COMPAT 定数"
  - "SH_DENYNO 定数"
  - "SH_DENYRD 定数"
  - "SH_DENYRW 定数"
  - "SH_DENYWR 定数"
  - "共有 (定数を)"
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 共有モード定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ファイル共有モードの定数です。  
  
## 構文  
  
```  
  
#include <share.h>  
  
```  
  
## 解説  
 *shflag* 引数は 1 つ以上の記号定数から構成され、共通モードを指定します。  共有モードは、*oflag* 引数と組み合わせて指定できます。詳細については、「[ファイル定数](../c-runtime-library/file-constants.md)」を参照してください。  
  
 次の表は、定数とその意味の一覧です。  
  
|定数|説明|  
|--------|--------|  
|`_SH_DENYRW`|ファイルの読み取りと書き込みを禁止|  
|`_SH_DENYWR`|ファイルの書き込みを禁止|  
|`_SH_DENYRD`|ファイルの読み取りを禁止|  
|`_SH_DENYNO`|読み取りと書き込みを許可|  
|`_SH_SECURE`|安全なモード \(共有の読み取りアクセス、排他的な書き込みアクセス\) を設定します。|  
  
## 参照  
 [\_sopen、\_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [\_fsopen、\_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)