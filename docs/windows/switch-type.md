---
title: "switch_type |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.switch_type
dev_langs: C++
helpviewer_keywords: switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 99ec139c1ff10456639249c94451877a18cbbf51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="switchtype"></a>switch_type
共用体の判別変数として使用される変数の型を識別します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[switch_type(  
type  
}]  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `type`  
 スイッチの種類は、整数、文字、ブール値、または列挙型を指定できます。  
  
## <a name="remarks"></a>コメント  
 **Switch_type** C++ 属性と同じ機能を持つ、 [switch_type](http://msdn.microsoft.com/library/windows/desktop/aa367276) MIDL 属性。  
  
 C++ 属性をサポートしていない[共用体をカプセル化された](http://msdn.microsoft.com/library/windows/desktop/aa366811)です。 [カプセル化されていない共用体](http://msdn.microsoft.com/library/windows/desktop/aa367119)次の形式でのみサポートされます。  
  
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
  
## <a name="example"></a>例  
 参照してください、[ケース](../windows/case-cpp.md)のサンプルの使用例**switch_type**です。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`typedef`|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [export](../windows/export.md)   
