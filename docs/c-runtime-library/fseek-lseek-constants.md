---
title: "fseek 定数と _lseek 定数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SEEK_END"
  - "SEEK_SET"
  - "SEEK_CUR"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "SEEK_CUR 定数"
  - "SEEK_END 定数"
  - "SEEK_SET 定数"
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fseek 定数と _lseek 定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <stdio.h>  
  
```  
  
## 解説  
 *元の* 引数は初期位置を指定する、次のマニフェスト定数の 1 つがです:  
  
|定数|説明|  
|--------|--------|  
|`SEEK_END`|EOF が見つかりました。|  
|`SEEK_CUR`|ファイル ポインターの現在の位置|  
|`SEEK_SET`|ファイルの先頭|  
  
## 参照  
 [fseek、\_fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_lseek、\_lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)