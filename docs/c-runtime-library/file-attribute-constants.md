---
title: "ファイル属性定数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A_HIDDEN"
  - "_A_NORMAL"
  - "_A_SUBDIR"
  - "_A_RDONLY"
  - "A_NORMAL"
  - "A_SUBDIR"
  - "_A_SYSTEM"
  - "c.constants.file"
  - "_A_HIDDEN"
  - "A_RDONLY"
  - "_A_ARCH"
  - "A_ARCH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_A_ARCH 定数"
  - "_A_HIDDEN 定数"
  - "_A_NORMAL 定数"
  - "_A_RDONLY 定数"
  - "_A_SUBDIR 定数"
  - "_A_SYSTEM 定数"
  - "定数 [C++], ファイル属性"
  - "ファイル属性定数 [C++]"
  - "ファイル [C++], ファイル属性定数"
ms.assetid: 8dc8ccb9-99f5-446b-876c-7ebecc2f764f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ファイル属性定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <io.h>  
```  
  
## 解説  
 これらの定数は、関数によって指定されたファイルまたはディレクトリの属性を指定します。  
  
 属性は次の記号定数で表されます。:  
  
 `_A_ARCH`  
 アーカイブ。  ファイルのバックアップ コマンドで変更され、オフたびに設定します。  値: 0x20  
  
 `_A_HIDDEN`  
 隠しファイル。  \/AH オプションを使用しない場合、dir コマンドとして参照されなくて。  これを正しくファイル、またはファイルに関する情報は属性。  値: 0x02  
  
 `_A_NORMAL`  
 標準です。  ファイルが無制限に読み取ったり書き込んだりできます。  値: 0x00  
  
 `_A_RDONLY`  
 読み取り専用。  ファイルが書き込み用に開くと同じ名前のファイルを作成できません。  値: 0x01  
  
 `_A_SUBDIR`  
 サブディレクトリ。  値: 0x10  
  
 `_A_SYSTEM`  
 システム ファイル。  \/AS オプションを使用しない場合、dir コマンドとして参照されなくて。  値: 0x04  
  
 複数の定数または演算子と組み合わせることができます。&#124;\)。  
  
## 参照  
 [ファイル名検索関数](../c-runtime-library/filename-search-functions.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)