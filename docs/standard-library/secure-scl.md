---
title: "_SECURE_SCL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SECURE_SCL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_SECURE_SCL"
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# _SECURE_SCL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[チェックを行う反復子](../standard-library/checked-iterators.md) が有効かどうかを定義します。  を定義する場合は、1 として、安全でない反復子を使用すると、ランタイム エラーになり、プログラムが終了します。  を定義する場合は、0 として、チェックを行う反復子は無効になります。  デバッグ モードでは、**\_SECURE\_SCL** の既定値は 1、チェックを行う反復子が有効であることを意味しています。  リリース モードでは、`_SECURE_SCL` の既定値は 0 です。  
  
> [!IMPORTANT]
>  `_SECURE_SCL`を制御するために `_ITERATOR_DEBUG_LEVEL` を使用します。  詳細については、「[\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)」を参照してください。  
  
## 解説  
 有効にするには、反復子を 1 に設定します **\_SECURE\_SCL** を確認する:  
  
```  
#define _SECURE_SCL 1  
```  
  
 無効になるには反復子を 0 に設定します **\_SECURE\_SCL** を確認する:  
  
```  
#define _SECURE_SCL 0  
```  
  
 チェックを行う反復子の警告を無効にする方法の詳細については [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md)を参照してください。  
  
## 参照  
 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)   
 [チェックを行う反復子](../standard-library/checked-iterators.md)   
 [反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)   
 [安全なライブラリ: C\+\+ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)