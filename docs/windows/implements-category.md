---
title: "implements_category |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.implements_category
dev_langs: C++
helpviewer_keywords: implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6ab6206851385dcf7bf73cf56730093e7fc5c48f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="implementscategory"></a>implements_category
ターゲット クラスによって実装されるコンポーネントのカテゴリを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ implements_category(  
   implements_category="uuid"  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 **implements_category**  
 実装済みのカテゴリの ID。  
  
## <a name="remarks"></a>コメント  
 **Implements_category** C++ 属性がターゲット クラスによって実装されるコンポーネントのカテゴリを指定します。 これは、カテゴリのマップを作成してで指定された別のエントリを追加することで、 **implements_category**属性。 詳細については、次を参照してください。[コンポーネントのカテゴリと方法は、作業は何ですか?](http://msdn.microsoft.com/library/windows/desktop/ms694322)です。  
  
 この属性を使用するには、 [coclass](../windows/coclass.md)、 [progid](../windows/progid.md)、または [vi_progid](../windows/vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば、 **progid** を適用すると、 **vi_progid** と **coclass** も適用されます。  
  
## <a name="example"></a>例  
 次のコードでは、次のオブジェクトがコントロール カテゴリを実装することを指定します。  
  
```  
// cpp_attr_ref_implements_category.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="MyLib")];  
[ coclass, implements_category("CATID_Control"),  
  uuid("20a0d0cc-5172-40f5-99ae-5e032f3205ae")]  
class CMyClass {};  
```  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`|  
|**反復可能**|[はい]|  
|**必要な属性**|次のいずれかの:**コクラス**、 **progid**、または**vi_progid**|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [COM 属性](../windows/com-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [IMPLEMENTED_CATEGORY](../atl/reference/category-macros.md#implemented_category)   
 