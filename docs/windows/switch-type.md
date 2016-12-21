---
title: "switch_type | Microsoft Docs"
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
  - "vc-attr.switch_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "switch_type attribute"
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# switch_type
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

discriminant 共用体として使用されている変数の型を指定します。  
  
## 構文  
  
```  
  
[switch_type(  
type  
}]  
  
```  
  
#### パラメーター  
 `type`  
 スイッチは文字型整数ブール型列挙型のいずれかになります。  
  
## 解説  
 **switch\_type** C\+\+ 属性に [switch\_type](http://msdn.microsoft.com/library/windows/desktop/aa367276) の MIDL の属性と同じ機能があります。  
  
 C\+\+ 属性は [カプセル化された共用体](http://msdn.microsoft.com/library/windows/desktop/aa366811) をサポートしていません。  [Nonencapsulated の共用体](http://msdn.microsoft.com/library/windows/desktop/aa367119) は次の形式でのみサポートされています :  
  
```  
// cpp_attr_ref_switch_type.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLibrary")];  
[ export ]  
struct SizedValue2 {  
   [switch_type("char"), switch_is(kind)] union {  
      [case(1), string]  
         wchar_t* wval;  
      [default, string]  
         char* val;  
   };  
   char kind;  
};  
```  
  
## 使用例  
 **switch\_type** の使用例については [case](../windows/case-cpp.md) の例を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`typedef`|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [export](../windows/export.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)