---
title: "defaultvtable | Microsoft Docs"
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
  - "vc-attr.defaultvtable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "defaultvtable attribute"
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# defaultvtable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM オブジェクトの既定の vtable インターフェイスとインターフェイスを定義します。  
  
## 構文  
  
```  
  
      [ defaultvtable(  
   interface  
) ]  
```  
  
#### パラメーター  
 `interface`  
 COM オブジェクトの vtable に既定値を指定するインターフェイス。  
  
## 解説  
 **defaultvtable** C\+\+ 属性に [defaultvtable](http://msdn.microsoft.com/library/windows/desktop/aa366795) の MIDL の属性と同じ機能があります。  
  
## 使用例  
 次のコードは既定のインターフェイスを指定するために **defaultvtable** を使用するクラスの属性を示します :  
  
```  
// cpp_attr_ref_defaultvtable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI1 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface IMyI2 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000003")]  
__interface IMyI3 {  
   HRESULT x();  
};  
  
[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),  
uuid("00000000-0000-0000-0000-000000000004")]  
class CMyC3 : public IMyI3 {};  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**  `struct`|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|**コクラス**|  
|**無効な属性**|なし|  
  
 詳細については[属性コンテキスト](../windows/attribute-contexts.md) を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)