---
title: "propputref | Microsoft Docs"
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
  - "vc-attr.propputref"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "propputref attribute"
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# propputref
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

値ではなく参照を使用するプロパティ設定の関数を指定します。  
  
## 構文  
  
```  
  
[propputref]  
  
```  
  
## 解説  
 **propputref** C\+\+ 属性に [propputref](http://msdn.microsoft.com/library/windows/desktop/aa367147) の MIDL の属性と同じ機能があります。  
  
## 使用例  
 **propputref** の使用例の [bindable](../windows/bindable.md) の例を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|メソッド|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|**propget propput**|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [propget](../windows/propget.md)   
 [propput](../windows/propput.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)