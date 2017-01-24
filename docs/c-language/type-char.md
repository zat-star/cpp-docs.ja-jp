---
title: "char 型 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "char キーワード [C]"
  - "型 char"
  - "unsigned char キーワード [C]"
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# char 型
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`char` 型は、表現できる文字セットのメンバーの整数値を格納するために使用されます。  この整数値は、特定の文字に対応する ASCII コードです。  
  
 **Microsoft 固有の仕様 →**  
  
 `unsigned char` 型の文字値の範囲は、16 進数で 0 から 0xFF までです。  **signed char** には 0x80 から 0x7F までの範囲があります。  これらの範囲は、0 ～ 255 の 10 進数と –128 ～ \+127 の 10 進数にそれぞれ変換されます。  \/J コンパイラ オプションは、既定値を **signed** から `unsigned` に変更します。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [基本型の格納](../c-language/storage-of-basic-types.md)