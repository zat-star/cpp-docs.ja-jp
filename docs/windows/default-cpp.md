---
title: "default (C++) | Microsoft Docs"
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
  - "vc-attr.default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "default 属性"
  - "属性 [C#], 既定の属性"
  - "既定, 既定の属性"
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# default (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コクラス内で定義されるカスタムまたはディスパッチ インターフェイスが既定のプログラミング インターフェイスを表すことを示します。  
  
## 構文  
  
```  
  
[ default(  
interface1  
,  
   interface2  
) ]  
  
```  
  
#### パラメーター  
 *interface1*  
 **default** 属性で定義されているクラスに基づいてオブジェクトを作成するスクリプト環境で使用可能になる既定のインターフェイス。  
  
 既定のインターフェイスが指定されていない場合は、最初に見つかったソース以外のインターフェイスが既定値として使用されます。  
  
 *interface2* \(省略可能\)  
 既定のソース インターフェイス。 このインターフェイスを指定する場合は、[source](../Topic/source%20\(C++\).md) 属性も使用する必要があります。  
  
 既定のソース インターフェイスが指定されていない場合は、最初のソース インターフェイスが既定値として使用されます。  
  
## 解説  
 **default** C\+\+ 属性には、[default](http://msdn.microsoft.com/library/windows/desktop/aa366787) MIDL 属性と同じ機能があります。 また、**default** 属性は、[case](../windows/case-cpp.md) 属性と共に使用されます。  
  
## 使用例  
 次のコードは、**default** をコクラスの定義で使用して、**ICustomDispatch** を既定のプログラミング インターフェイスとして指定する方法を示しています。  
  
```  
// cpp_attr_ref_default.cpp  
// compile with: /LD  
#include "windows.h"  
[module(name="MyLibrary")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
  
[dual, uuid("9E66A291-4365-11D2-A997-00C04FA37DDB")]   
__interface IDual {  
   HRESULT Dual([in] long l, [out, retval] long *pLong);  
};  
  
[object, uuid("9E66A293-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustomDispatch : public IDispatch {  
   HRESULT Dispatch([in] long l, [out, retval] long *pLong);  
};  
  
[   coclass,  
   default(ICustomDispatch),   
   source(IDual),  
   uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")  
]  
class CClass : public ICustom, public IDual, public ICustomDispatch {  
   HRESULT Custom(long l, long *pLong) { return(S_OK); }  
   HRESULT Dual(long l, long *pLong) { return(S_OK); }  
   HRESULT Dispatch(long l, long *pLong) { return(S_OK); }  
};  
  
int main() {  
#if 0 // Can't instantiate without implementations of IUnknown/IDispatch  
   CClass *pClass = new CClass;  
  
   long llong;  
  
   pClass->custom(1, &llong);  
   pClass->dual(1, &llong);  
   pClass->dispinterface(1, &llong);  
   pClass->dispatch(1, &llong);  
  
   delete pClass;  
#endif  
   return(0);  
}  
```  
  
 **default** の使用例については、「[source](../Topic/source%20\(C++\).md)」も参照してくださいにも含まれています。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、`struct`、データ メンバー|  
|**反復可能**|いいえ|  
|**必要な属性**|**coclass** \(**class** または `struct` に適用される場合\)|  
|**無効な属性**|なし|  
  
 詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [coclass](../windows/coclass.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)