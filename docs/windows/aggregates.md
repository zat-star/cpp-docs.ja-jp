---
title: "aggregates | Microsoft Docs"
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
  - "vc-attr.aggregates"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregates 属性"
  - "集約 [C++]"
  - "集約オブジェクト [C++], aggregates 属性"
  - "集約 [C++]"
ms.assetid: 67a084c9-941f-474b-a029-9c93b38ebe9a
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# aggregates
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オブジェクトが CLSID で指定されたオブジェクトを集約することを示します。  
  
## 構文  
  
```  
  
[ aggregates(  
clsid,  
variable_name  
) ]  
  
```  
  
#### パラメーター  
 `clsid`  
 集約可能オブジェクトの CLSID を指定します。  
  
 `variable_name`  
 挿入する変数の名前。 この変数には、集約対象オブジェクトの **IUnknown** を格納します。  
  
## 解説  
 オブジェクトに適用すると、**aggregates** C\+\+ 属性は \(`clsid` によって指定された\) 集約対象オブジェクトのアウター ラッパーを実装します。  
  
 この属性を使用するには、[coclass](../windows/coclass.md)、[progid](../Topic/progid.md)、または [vi\_progid](../windows/vi-progid.md) 属性 \(または、これらのいずれかを意味する別の属性\) も同じ要素に適用する必要があります。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば、**progid** を適用すると、**vi\_progid** と **coclass** も適用されます。  
  
 **ATL プロジェクト**  
  
 この属性が ATL を使用するプロジェクト内で使用されている場合、属性の動作は変わります。 まず、次のエントリがターゲット オブジェクトの COM マップに追加されます。  
  
```  
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(_m_spAttrXXX, clsid)  
```  
  
 また、[DECLARE\_GET\_CONTROLLING\_UNKNOWN](../Topic/DECLARE_GET_CONTROLLING_UNKNOWN.md) マクロも追加されます。  
  
## 使用例  
  
```  
// cpp_attr_ref_aggregates.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
// requires 'aggregatable.dll'  
// see aggregatable attribute to create 'aggregatable.dll'  
class DECLSPEC_UUID("1a8369cc-1c91-42c4-befa-5a5d8c9d2529") CMyClass;  
  
[module (name="MYObject")];  
[object, uuid("ab006d85-e754-47c5-9ef4-2744ff32a20c")]  
__interface IObject  
{  
};  
  
[ coclass, aggregates(__uuidof(CMyClass)),   
  uuid("91cb2c06-8931-432a-baac-206e55c4edfb")]  
struct CObject : IObject  
{  
   int i;  
};  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、`struct`|  
|**反復可能**|はい|  
|**必要な属性**|**coclass**、**progid**、**vi\_progid** のうち 1 つ以上。|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [COM Attributes](../Topic/COM%20Attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [集約](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
 [Aggregatable](http://msdn.microsoft.com/library/windows/desktop/aa366721)   
 [COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)