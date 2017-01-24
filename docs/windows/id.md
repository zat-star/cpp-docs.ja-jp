---
title: "id | Microsoft Docs"
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
  - "vc-attr.id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "id attribute"
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# id
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メンバー関数 \(インターフェイスのプロパティまたはメソッドまたはディスパッチ インターフェイス\) に `dispid` のパラメーターを指定します。  
  
## 構文  
  
```  
  
      [ id(  
   dispid  
) ]  
```  
  
#### パラメーター  
 `dispid`  
 インターフェイス メソッドのディスパッチ ID。  
  
## 解説  
 **ID** C\+\+ 属性に [ID](http://msdn.microsoft.com/library/windows/desktop/aa367040) の MIDL の属性と同じ機能があります。  
  
## 使用例  
 **ID** を使用する方法の例に [bindable](../windows/bindable.md) の例を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイス メソッド|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については[属性コンテキスト](../windows/attribute-contexts.md) を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Data Member Attributes](../windows/data-member-attributes.md)   
 [defaultvalue](../Topic/defaultvalue.md)   
 [in](../Topic/in%20\(C++\).md)   
 [out](../Topic/out%20\(C++\).md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)