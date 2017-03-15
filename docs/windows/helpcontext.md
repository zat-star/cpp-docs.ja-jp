---
title: "helpcontext | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.helpcontext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "helpcontext attribute"
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# helpcontext
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ヘルプ ファイルに要素に関するユーザーの情報を表示できるようにするためのコンテキスト ID を指定します。  
  
## 構文  
  
```  
  
      [ helpcontext(  
   id  
) ]  
```  
  
#### パラメーター  
 `id`  
 ヘルプ トピックのコンテキスト ID。  コンテキスト ID の詳細については [HTML ヘルプ : プログラムの状況依存のヘルプ](../mfc/html-help-context-sensitive-help-for-your-programs.md) を参照してください。  
  
## 解説  
 **helpcontext\(X\)** C\+\+ 属性に [helpcontext\(X\)](http://msdn.microsoft.com/library/windows/desktop/aa366851) の MIDL の属性と同じ機能があります。  
  
## 使用例  
 **helpcontext\(X\)** を使用する方法の例に [defaultvalue](../Topic/defaultvalue.md) の例を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`interface` `typedef` のメソッドプロパティ **クラス**|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については[属性コンテキスト](../windows/attribute-contexts.md) を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [helpfile](../Topic/helpfile.md)   
 [helpstring](../windows/helpstring.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)