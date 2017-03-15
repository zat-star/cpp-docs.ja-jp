---
title: "_com_error::ErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error::ErrorInfo"
  - "ErrorInfo"
  - "_com_error.ErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ErrorInfo メソッド"
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::ErrorInfo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 コンストラクターに渡された **IErrorInfo** オブジェクトを取得します。  
  
## 構文  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## 戻り値  
 コンストラクターに渡された未処理の **IErrorInfo** 項目。  
  
## 解説  
 `_com_error` オブジェクト内のカプセル化された **IErrorInfo** 項目 \(**IErrorInfo** 項目が記録されていない場合は **NULL**\) を取得します。  呼び出し元は、返されたオブジェクトを使い終わったら、そのオブジェクトの **Release** を呼び出す必要があります。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_com\_error クラス](../cpp/com-error-class.md)