---
title: "_com_error::GUID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "GUID"
  - "_com_error.GUID"
  - "_com_error::GUID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GUID メソッド"
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::GUID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 **IErrorInfo::GetGUID** 関数を呼び出します。  
  
## 構文  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## 戻り値  
 `_com_error` オブジェクト内に記録された **IErrorInfo** オブジェクトに対する **IErrorInfo::GetGUID** の結果を返します。  **IErrorInfo** オブジェクトが記録されていない場合は、`GUID_NULL` を返します。  
  
## 解説  
 **IErrorInfo::GetGUID** メソッドを呼び出すときの失敗は無視されます。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_com\_error クラス](../cpp/com-error-class.md)