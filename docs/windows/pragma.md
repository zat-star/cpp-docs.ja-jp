---
title: "プラグマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.pragma
dev_langs: C++
helpviewer_keywords: pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9069090fc0d2c405aa31dbf8d0447c28d8e0ef41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="pragma"></a>pragma
生成された .idl ファイルの引用符を使用せずに、指定した文字列を出力します。 。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ pragma(  
   pragma_statement  
) ];  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pragma_statement*  
 このプラグマは、生成された .idl ファイルに移動します。  
  
## <a name="remarks"></a>コメント  
 **プラグマ**C++ 属性と同じ機能を持つ、[プラグマ](http://msdn.microsoft.com/library/windows/desktop/aa367143)MIDL 属性。  
  
## <a name="example"></a>例  
  
```  
// cpp_attr_ref_pragma.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[pragma(pack(4))];  
  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A  
{  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|任意の場所|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [スタンドアロン属性](../windows/stand-alone-attributes.md)   
 [pack](../preprocessor/pack.md)   
