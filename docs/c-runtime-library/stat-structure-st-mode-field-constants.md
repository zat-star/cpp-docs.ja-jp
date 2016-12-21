---
title: "_stat 構造体の st_mode フィールド定数 | Microsoft Docs"
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
  - "S_IFCHR"
  - "S_IFDIR"
  - "_S_IWRITE"
  - "S_IFMT"
  - "_S_IFDIR"
  - "_S_IREAD"
  - "S_IEXEC"
  - "_S_IEXEC"
  - "_S_IFMT"
  - "S_IWRITE"
  - "S_IFREG"
  - "S_IREAD"
  - "_S_IFCHR"
  - "_S_IFREG"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_S_IEXEC 定数"
  - "_S_IFCHR 定数"
  - "_S_IFDIR 定数"
  - "_S_IFMT 定数"
  - "_S_IFREG 定数"
  - "_S_IREAD 定数"
  - "_S_IWRITE 定数"
  - "S_IEXEC 定数"
  - "S_IFCHR 定数"
  - "S_IFDIR 定数"
  - "S_IFMT 定数"
  - "S_IFREG 定数"
  - "S_IREAD 定数"
  - "S_IWRITE 定数"
  - "st_mode フィールド定数"
  - "stat 構造体"
  - "stat 構造体, 定数"
ms.assetid: fd462004-7563-4766-8443-30b0a86174b6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _stat 構造体の st_mode フィールド定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <sys/stat.h>  
  
```  
  
## 解説  
 これらの定数を [\_stat 構造体](../c-runtime-library/standard-types.md)の **st\_mode** フィールドにファイルの種類を示すために使用されます。  
  
 ビット マスク定数について説明します。:  
  
|定数|説明|  
|--------|--------|  
|`_S_IFMT`|ファイルの種類マスク|  
|`_S_IFDIR`|ディレクトリ|  
|`_S_IFCHR`|特殊文字セット \(デバイスを示します\)|  
|`_S_IFREG`|Regular|  
|`_S_IREAD`|Read、所有者|  
|`_S_IWRITE`|アクセス許可、所有者を記述します。|  
|`_S_IEXEC`|アクセス許可、所有者の実行またはの検索|  
  
## 参照  
 [\_stat、\_wstat 関数](../c-runtime-library/reference/stat-functions.md)   
 [\_fstat、\_fstat32、\_fstat64、\_fstati64、\_fstat32i64、\_fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [基本データ型](../c-runtime-library/standard-types.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)