---
title: "defaultcollelem | Microsoft Docs"
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
  - "vc-attr.defaultcollelem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "defaultcollelem attribute"
ms.assetid: 3dbbd293-8b83-4f70-a36b-64cc1d0b6713
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# defaultcollelem
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Basic コードの最適化に使用されます。  
  
## 構文  
  
```  
  
[defaultcollelem]  
  
```  
  
## 解説  
 **defaultcollelem\(L\)** C\+\+ 属性に [defaultcollelem\(L\)](http://msdn.microsoft.com/library/windows/desktop/aa366792) の MIDL の属性と同じ機能があります。  
  
## 使用例  
 次のコードは **defaultcollelem\(L\)** の属性を使用してインターフェイス メソッドを示しています :  
  
```  
// cpp_attr_ref_defaultcollelem.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyForm   
{     
   [propget, id(1), bindable, defaultcollelem, displaybind,   
   defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);  
   [propput, id(1), bindable, defaultcollelem, displaybind,   
   defaultbind, requestedit] HRESULT P1([in] long nSize);  
};  
```  
  
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
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)