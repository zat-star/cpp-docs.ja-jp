---
title: "集計可能では |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.aggregatable
dev_langs: C++
helpviewer_keywords: aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ec044e18fdd8bcd21fbad8d2e46c847c876cc00d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="aggregatable"></a>aggregatable
クラスが集計をサポートしていることを示します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ aggregatable(   
   value  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *値*(省略可能)  
 COM オブジェクトを集計できる場合を示すためにパラメーター:  
  
-   **決して**この COM オブジェクトを集計することはできません。  
  
-   **許可される**この COM オブジェクトを直接作成するか、集計することができます。 既定値です。  
  
-   **常に**この COM オブジェクトが直接作成することはできませんし、集計だけことができます。 呼び出すと`CoCreateInstance`このオブジェクトは集約オブジェクトを指定する必要があります**IUnknown**インターフェイス (制御**IUnknown**)。  
  
## <a name="remarks"></a>コメント  
 **集約可能**C++ 属性と同じ機能を持つ、[集約可能](http://msdn.microsoft.com/library/windows/desktop/aa366721)MIDL 属性。 ため、コンパイラは引数として渡すこと、**集約可能**属性から生成された .idl ファイルにします。  
  
 この属性を使用するには、 [coclass](../windows/coclass.md)、 [progid](../windows/progid.md)、または [vi_progid](../windows/vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば、 **progid** を適用すると、 **vi_progid** と **coclass** も適用されます。  
  
 **ATL プロジェクト**  
  
 この属性が ATL を使用するプロジェクト内で使用されている場合、属性の動作は変わります。 上記の動作だけでなく属性も追加マクロを次のいずれかに対象クラス。  
  
|パラメーター値|挿入されるマクロ|  
|---------------------|--------------------|  
|**ぜんぜん**|[DECLARE_NOT_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_not_aggregatable)|  
|**許可されます。**|[DECLARE_POLY_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_poly_aggregatable)|  
|**常時**|[集約](../atl/reference/aggregation-and-class-factory-macros.md#declare_only_aggregatable)|  
  
## <a name="example"></a>例  
  
```  
// cpp_attr_ref_aggregatable.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="MyModule")];  
  
[ coclass, aggregatable(allowed),  
  uuid("1a8369cc-1c91-42c4-befa-5a5d8c9d2529")]  
class CMyClass {};  
```  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`|  
|**反復可能**|×|  
|**必要な属性**|**coclass**、 **progid**、 **vi_progid**のうち 1 つ以上。|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [集計](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
