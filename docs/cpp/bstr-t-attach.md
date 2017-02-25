---
title: "_bstr_t::Attach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach メソッド"
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _bstr_t::Attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `_bstr_t` ラッパーを `BSTR` にリンクします。  
  
## 構文  
  
```  
  
      void Attach(  
   BSTR s  
);  
```  
  
#### パラメーター  
 *s*  
 `_bstr_t` 変数に関連付けられる、または割り当てられる `BSTR`。  
  
## 解説  
 `_bstr_t` が以前別の `BSTR` にアタッチされている場合、`_bstr_t` は、`_bstr_t` の他の変数が `BSTR` を使用していない場合 `BSTR` リソースをクリーンアップします。  
  
## 使用例  
 **Attach** の使用例については、「[\_bstr\_t::Assign](../cpp/bstr-t-assign.md)」を参照してください。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_bstr\_t クラス](../cpp/bstr-t-class.md)