---
title: "retval | Microsoft Docs"
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
  - "vc-attr.retval"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "retval attribute"
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# retval
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メンバーの戻り値を受け取るパラメーターを指定します。  
  
## 構文  
  
```  
  
[retval]  
  
```  
  
## 解説  
 **retval** C\+\+ 属性に [retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) の MIDL の属性と同じ機能があります。  
  
 **retval** は関数の宣言の最後の引数で使用する必要があります。  
  
## 使用例  
 **retval** の使用例の [bindable](../windows/bindable.md) の例を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイス パラメーター、インターフェイス メソッド|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|**\[out\]**|  
|**無効な属性**|**\[in\]**|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)