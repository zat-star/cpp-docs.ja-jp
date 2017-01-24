---
title: "定数とグローバル変数のマップ | Microsoft Docs"
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
  - "_tenviron"
  - "_TEOF"
  - "_tfinddata_t"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tenviron 関数"
  - "_TEOF 型"
  - "_tfinddata_t 関数"
  - "汎用テキスト マップ"
  - "tenviron 関数"
  - "TEOF 型"
  - "tfinddatat 関数"
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 定数とグローバル変数のマップ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのグローバル変数、定数汎用テキストと基本データ型の割り当ては TCHAR.H で定義され、定数 `_UNICODE` または `_MBCS` がプログラム内で定義されているかどうかによって異なります。  
  
### 定数汎用テキストとグローバル変数のマッピング  
  
|汎用テキスト\-オブジェクト名|SBCS \(定義されていない\_UNICODE、\_MBCS\)|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|---------------------|---------------------------------------|-----------------------|--------------------------|  
|`_TEOF`|`EOF`|`EOF`|`WEOF`|  
|`_tenviron`|`_environ`|`_environ`|`_wenviron`|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## 参照  
 [汎用テキスト マップ](../c-runtime-library/generic-text-mappings.md)   
 [データ型のマップ](../c-runtime-library/data-type-mappings.md)   
 [ルーチンのマップ](../c-runtime-library/routine-mappings.md)   
 [汎用テキストのプログラム例](../c-runtime-library/a-sample-generic-text-program.md)   
 [汎用テキスト マップの使用](../c-runtime-library/using-generic-text-mappings.md)