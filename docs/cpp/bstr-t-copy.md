---
title: "_bstr_t::copy | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSTR オブジェクト, copy"
  - "Copy メソッド"
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _bstr_t::copy
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 カプセル化された `BSTR` のコピーを生成します。  
  
## 構文  
  
```  
  
      BSTR copy(  
  bool fCopy = true  
) const;  
```  
  
#### パラメーター  
 `fCopy`  
 **true** の場合、**copy** は含まれている `BSTR` のコピーを返します。それ以外の場合、**copy** は実際の BSTR を返します。  
  
## 解説  
 カプセル化された `BSTR` オブジェクトの新しく割り当てられたコピーを返します。  
  
## 使用例  
  
```  
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t  
   *pVal = m_bsConStr.copy();  
}  
```  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_bstr\_t クラス](../cpp/bstr-t-class.md)