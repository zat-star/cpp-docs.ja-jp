---
title: "_com_error::HelpContext | Microsoft Docs"
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
  - "_com_error::HelpContext"
  - "HelpContext"
  - "_com_error.HelpContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HelpContext メソッド"
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::HelpContext
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 **IErrorInfo::GetHelpContext** 関数を呼び出します。  
  
## 構文  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## 戻り値  
 `_com_error` オブジェクト内に記録された **IErrorInfo** オブジェクトに対する **IErrorInfo::GetHelpContext** の結果を返します。  **IErrorInfo** オブジェクトが記録されていない場合は、ゼロを返します。  
  
## 解説  
 **IErrorInfo::GetHelpContext** メソッドを呼び出すときの失敗は無視されます。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_com\_error クラス](../cpp/com-error-class.md)