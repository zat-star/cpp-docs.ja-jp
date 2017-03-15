---
title: "数値演算エラー M6108 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6108"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6108"
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 数値演算エラー M6108
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

square root  
  
 負の値の平方根を計算しようとしました。  
  
 プログラムは終了コード 136 で終了します。  
  
> [!NOTE]
>  C ランタイム ライブラリ関数 `sqrt` と FORTRAN 組み込み関数 **SQRT** では、このエラーは発生しません。  C 関数 `sqrt` は計算の前に引数をチェックし、その値が負の場合はエラー値を返します。  FORTRAN 関数 **SQRT** では、このエラーではなく DOMAIN エラー [数値演算エラー M6201](../../error-messages/tool-errors/math-error-m6201.md) が発生します。