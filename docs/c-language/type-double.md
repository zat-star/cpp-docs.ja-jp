---
title: "double 型 | Microsoft Docs"
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
  - "Double 型"
  - "仮数部, 浮動小数点変数"
  - "移植性 [C++], 型 double"
  - "型 double"
ms.assetid: 17c85b24-1475-4d41-a03c-ddf2d6561d34
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# double 型
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

double 型の倍精度浮動小数点値のサイズは 8 バイトです。  形式は、float 形式に似ています。ただし、エクセス 1023 形式の 11 ビット指数部と 52 ビット仮数部に、暗黙の上位 1 ビットを持ちます。  この形式では、およそ 1.7E\-308 ～ 1.7E\+308 の範囲を double 型で表現します。  
  
 **Microsoft 固有の仕様 →**  
  
 double 型は 64 ビットで、符号が 1 ビット、指数部が 11 ビット、仮数部が 52 ビットです。  その範囲は 15 桁以上の精度で、\+\/–1.7E308 です。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [基本型の格納](../c-language/storage-of-basic-types.md)