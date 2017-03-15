---
title: "_bstr_t::operator ! | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::operator!"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "! 演算子"
  - "! 演算子, bstr"
  - "operator!, bstr"
ms.assetid: 6e60b5a5-2d28-4eec-9e12-790da8f1fdd4
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::operator !
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 カプセル化された `BSTR` が **NULL** 文字列であるかどうかを調べます。  
  
## 構文  
  
```  
  
bool operator!( ) const throw( );  
  
```  
  
## 戻り値  
 そうである場合は **true**、それ以外の場合は **false** を返します。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_bstr\_t クラス](../cpp/bstr-t-class.md)