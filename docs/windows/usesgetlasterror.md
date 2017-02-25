---
title: "usesgetlasterror | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.usesgetlasterror"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "usesgetlasterror attribute"
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# usesgetlasterror
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

エラー コードを取得するために呼び出し元は`GetLastError` を呼び出す場合は関数を呼び出すときにエラーがある場合は呼び出し元は指示します。  
  
## 構文  
  
```  
  
[usesgetlasterror]  
  
```  
  
## 解説  
 **usesgetlasterror** C\+\+ 属性に [usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) の MIDL の属性と同じ機能があります。  
  
## 使用例  
 **usesgetlasterror** を使用する方法の例については [idl\_module](../windows/idl-module.md) の例を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**モジュール**  の属性|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)