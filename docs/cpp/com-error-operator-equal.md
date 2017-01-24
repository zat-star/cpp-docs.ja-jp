---
title: "_com_error::operator = | Microsoft Docs"
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
  - "_com_error::operator="
  - "_com_error.operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= 演算子, Visual C++ 固有のオブジェクトを使用する"
  - "演算子 = _com_error オブジェクト"
  - "演算子 = _com_error オブジェクト"
ms.assetid: b9cc4094-d055-450c-b45a-0a95317488f8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::operator =
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 既存の `_com_error` オブジェクトを別のオブジェクトに割り当てます。  
  
## 構文  
  
```  
  
      _com_error& operator = (  
   const _com_error& that   
) throw ( );  
```  
  
#### パラメーター  
 `that`  
 `_com_error` オブジェクト。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_com\_error クラス](../cpp/com-error-class.md)