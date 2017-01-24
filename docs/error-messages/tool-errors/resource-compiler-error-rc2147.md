---
title: "リソース コンパイラ エラー RC2147 | Microsoft Docs"
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
  - "RC2147"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2147"
ms.assetid: 09974f06-1731-4e70-b373-f9218e0ee8d9
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リソース コンパイラ エラー RC2147
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

SUBLANGUAGE ID not a number  
  
 副言語 ID の値は数字である必要があります。  
  
 **LANGUAGE** ステートメントには、次に示す構文を使う必要があります。  
  
 **LANGUAGE** *primary\_language\_ID*,*secondary\_language\_ID*  
  
 有効な副言語 ID の値は、WINNT.h ファイルの中で **SUBLANG\_** 定数として定義されています。