---
title: "_bstr_t::GetAddress | Microsoft Docs"
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
  - "_bstr_t::GetAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAddress メソッド"
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::GetAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 既存の文字列を解放し、新しく割り当てられた文字列のアドレスを返します。  
  
## 構文  
  
```  
  
BSTR* GetAddress( );  
  
```  
  
## 戻り値  
 `_bstr_t` でラップされた `BSTR` へのポインター。  
  
## 解説  
 `GetAddress` は、`BSTR` を共有するすべての `_bstr_t` オブジェクトに影響します。  複数の `_bstr_t` がコピー コンストラクターおよび `operator=` を使用して `BSTR` を共有できます。  
  
## 使用例  
 `GetAddress` の使用例については、「[\_bstr\_t::Assign](../cpp/bstr-t-assign.md)」を参照してください。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_bstr\_t クラス](../cpp/bstr-t-class.md)