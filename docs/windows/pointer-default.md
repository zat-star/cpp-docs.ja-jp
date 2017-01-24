---
title: "pointer_default | Microsoft Docs"
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
  - "vc-attr.pointer_default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_default attribute"
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# pointer_default
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

パラメーター リストに表示される最上位のポインターを除くすべての既定のポインターの属性を指定します。  
  
## 構文  
  
```  
  
      [ pointer_default(  
   value  
) ]  
```  
  
#### パラメーター  
 *value*  
 ポインター型を記述する値 : **ptr**`ref`または  **一意** 。  
  
## 解説  
 **pointer\_default** C\+\+ 属性に [pointer\_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) の MIDL の属性と同じ機能があります。  
  
## 使用例  
 **pointer\_default** の使用例の [defaultvalue](../Topic/defaultvalue.md) の例を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`interface`|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)