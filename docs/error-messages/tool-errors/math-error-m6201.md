---
title: "数値演算エラー M6201 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6201"
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 数値演算エラー M6201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : \_DOMAIN エラー  
  
 指定された関数の引数の値が、許容範囲を超えています。  
  
## 使用例  
  
```  
result = sqrt(-1.0)   // C statement  
result = SQRT(-1.0)   !  FORTRAN statement  
```  
  
 このエラーが発生すると、関数 `_matherr` が呼び出され、関数名、引数、エラー タイプが渡されます。  関数 `_matherr` を書き直すことによって、実行時浮動小数点数値演算エラーの処理をカスタマイズできる場合もあります。