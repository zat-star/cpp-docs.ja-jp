---
title: "_bstr_t::operator = | Microsoft Docs"
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
  - "_bstr_t::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= 演算子, Visual C++ 固有のオブジェクトを使用する"
  - "演算子 =, bstr"
  - "演算子 =, bstr"
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::operator =
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 既存の `_bstr_t` オブジェクトに新しい値を代入します。  
  
## 構文  
  
```  
  
      _bstr_t& operator=(  
   const _bstr_t& s1   
) throw ( );  
_bstr_t& operator=(  
   const char* s2   
);  
_bstr_t& operator=(  
   const wchar_t* s3   
);  
_bstr_t& operator=(  
   const _variant_t& var   
);  
```  
  
#### パラメーター  
 *s1*  
 既存の `_bstr_t` オブジェクトに割り当てられる `_bstr_t` オブジェクト。  
  
 *s2*  
 既存の `_bstr_t` オブジェクトに割り当てられるマルチバイト文字列。  
  
 `s3`  
 既存の `_bstr_t` オブジェクトに割り当てられる Unicode 文字列。  
  
 `var`  
 既存の `_bstr_t` オブジェクトに割り当てられる `_variant_t` オブジェクト。  
  
 **END Microsoft 固有の仕様**  
  
## 使用例  
 `operator=` の使用例については、「[\_bstr\_t::Assign](../cpp/bstr-t-assign.md)」を参照してください。  
  
## 参照  
 [\_bstr\_t クラス](../cpp/bstr-t-class.md)