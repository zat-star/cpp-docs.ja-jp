---
title: "dispinterface | Microsoft Docs"
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
  - "vc-attr.dispinterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dispinterface 属性"
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# dispinterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ディスパッチ インターフェイスとしてインターフェイスを .idl ファイルに配置します。  
  
## 構文  
  
```  
  
[dispinterface]  
  
```  
  
## 解説  
 **dispinterface** C\+\+ 属性がインターフェイスの前にあると、インターフェイスは生成される .idl ファイルのライブラリ ブロック内に配置されます。  
  
 基底クラスを指定しないと、ディスパッチ インターフェイスは `IDispatch` から派生します。 ディスパッチ インターフェイスのメンバーの [id](../windows/id.md) を指定する必要があります。  
  
 MIDL のドキュメントには [dispinterface](http://msdn.microsoft.com/library/windows/desktop/aa366802) の次のような使用例があります。  
  
```  
dispinterface helloPro   
   { interface hello; };   
```  
  
 これは、**dispinterface** 属性の有効な使用方法ではありません。  
  
## 使用例  
 **dispinterface** の使用方法の例については、[bindable](../windows/bindable.md) の例を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`interface`|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|**dual**、**object**、**oleautomation**、`local`、**ms\_union**|  
  
 詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Attributes by Usage](../windows/attributes-by-usage.md)   
 [uuid](../windows/uuid-cpp-attributes.md)   
 [dual](../Topic/dual.md)   
 [custom](../windows/custom-cpp.md)   
 [object](../Topic/object%20\(C++\).md)   
 [\_\_interface](../Topic/__interface.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)