---
title: "propput | Microsoft Docs"
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
  - "vc-attr.propput"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "propput attribute"
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# propput
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロパティ設定関数を指定します。  
  
## 構文  
  
```  
  
[propput]  
  
```  
  
## 解説  
 **propput** C\+\+ 属性には、[propput](http://msdn.microsoft.com/library/windows/desktop/aa367146) MIDL 属性と同じ機能があります。  
  
## 使用例  
 **propput** の使用サンプルについては、「[bindable](../windows/bindable.md)」の例を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|メソッド|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|**propget**、**propputref**|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [propget](../windows/propget.md)   
 [propputref](../windows/propputref.md)