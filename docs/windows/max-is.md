---
title: "max_is | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.max_is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_is attribute"
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# max_is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

有効な配列インデックスの最大値を指定します。  
  
## 構文  
  
```  
  
      [ max_is(  
   "expression"  
) ]  
```  
  
#### パラメーター  
 *expression*  
 一つ以上の C 言語の式。  空の引数のスロットを使用できます。  
  
## 解説  
 **max\_is** C\+\+ 属性に [max\_is](http://msdn.microsoft.com/library/windows/desktop/aa367074) の MIDL の属性と同じ機能があります。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`struct` または  **共用体**  インターフェイスのパラメーターインターフェイス メソッドのフィールドについて。|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|**size\_is**|  
  
 詳細については[属性コンテキスト](../windows/attribute-contexts.md) を参照してください。  
  
## 使用例  
 配列の一部を指定する方法の例については [first\_is](../windows/first-is.md) を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [first\_is](../windows/first-is.md)   
 [last\_is](../windows/last-is.md)   
 [length\_is](../windows/length-is.md)   
 [size\_is](../Topic/size_is.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)