---
title: "ファイル定数 | Microsoft Docs"
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
  - "_O_EXCL"
  - "_O_RDWR"
  - "_O_APPEND"
  - "_O_RDONLY"
  - "_O_TRUNC"
  - "_O_CREAT"
  - "_O_WRONLY"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_O_APPEND 定数"
  - "_O_CREAT 定数"
  - "_O_EXCL 定数"
  - "_O_RDONLY 定数"
  - "_O_RDWR 定数"
  - "_O_TRUNC 定数"
  - "_O_WRONLY 定数"
  - "O_APPEND 定数"
  - "O_CREAT 定数"
  - "O_EXCL 定数"
  - "O_RDONLY 定数"
  - "O_RDWR 定数"
  - "O_TRUNC 定数"
  - "O_WRONLY 定数"
ms.assetid: c8fa5548-9ac2-4217-801d-eb45e86f2fa4
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ファイル定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <fcntl.h>  
  
```  
  
## 解説  
 これらの定数の一つ以上から形成される整数式が許可される読み取りまたは書き込み操作の種類を決定します。  これは変換モード定数と一つ以上の定数を組み合わせることによって作成されます。  
  
 ファイル定数は次のとおりです。:  
  
 `_O_APPEND`  
 任意の書き込み操作の前にファイルの末尾にファイル ポインターを移動します。  
  
 `_O_CREAT`  
 書き込み用の新しいファイルを作成し、開きます; これは *ファイル名* で指定されたファイルがある場合は影響しません。  
  
 `_O_EXCL`  
 *ファイル名* で指定されたファイルがある場合は、エラー値を返します。  `_O_CREAT`とともに使用された場合にのみ適用されます。  
  
 `_O_RDONLY`  
 読み取り専用のファイルを開くを; このフラグは、指定 `_O_RDWR` が `_O_WRONLY` も指定できます。  
  
 `_O_RDWR`  
 読み取りと書き込みの両方のモードでファイルを開くを; このフラグは、指定 `_O_RDONLY` が `_O_WRONLY` も指定できます。  
  
 `_O_TRUNC`  
 長さに既存のファイルを開き、切り捨てられる; ファイルはアクセス許可を記述する必要があります。  ファイルの内容が破棄されます。  このフラグが指定されている場合、`_O_RDONLY`を指定できません。  
  
 `_O_WRONLY`  
 書き込み用のファイルだけを開くを; このフラグは、指定 `_O_RDONLY` が `_O_RDWR` も指定できます。  
  
## 参照  
 [\_open、\_wopen](../c-runtime-library/reference/open-wopen.md)   
 [\_sopen、\_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)