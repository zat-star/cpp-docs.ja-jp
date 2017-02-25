---
title: "_com_error::Source | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error.Source"
  - "_com_error::Source"
  - "source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Source メソッド"
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::Source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 **IErrorInfo::GetSource** 関数を呼び出します。  
  
## 構文  
  
```  
  
_bstr_t Source() const;  
  
```  
  
## 戻り値  
 `_com_error` オブジェクト内に記録された **IErrorInfo** オブジェクトに対する **IErrorInfo::GetSource** の結果を返します。  結果の BSTR は `_bstr_t` オブジェクトにカプセル化されます。  **IErrorInfo** が記録されていない場合は、空の `_bstr_t` を返します。  
  
## 解説  
 **IErrorInfo::GetSource** メソッドを呼び出すときの失敗は無視されます。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_com\_error クラス](../cpp/com-error-class.md)