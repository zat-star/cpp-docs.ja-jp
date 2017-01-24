---
title: "_com_error::HRESULTToWCode | Microsoft Docs"
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
  - "HRESULTToWCode"
  - "_com_error.HRESULTToWCode"
  - "_com_error::HRESULTToWCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HRESULTToWCode メソッド"
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::HRESULTToWCode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 32 ビットの `HRESULT` を 16 ビットの `wCode` にマップします。  
  
## 構文  
  
```  
  
      static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### パラメーター  
 `hr`  
 16 ビットの `wCode` にマップされる 32 ビットの `HRESULT`。  
  
## 戻り値  
 32 ビットの `HRESULT` からマップされた 16 ビットの `wCode`。  
  
## 解説  
 詳細については、「[\_com\_error::WCode](../cpp/com-error-wcode.md)」を参照してください。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_com\_error::WCode](../cpp/com-error-wcode.md)   
 [\_com\_error::WCodeToHRESULT](../Topic/_com_error::WCodeToHRESULT.md)   
 [\_com\_error クラス](../cpp/com-error-class.md)