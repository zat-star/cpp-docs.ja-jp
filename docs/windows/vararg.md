---
title: "vararg |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.vararg
dev_langs: C++
helpviewer_keywords: vararg attribute
ms.assetid: 20fc3244-18e9-411c-990e-d5b4fa29a570
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 96689914ae299700f2640fa205cbad8887692454
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="vararg"></a>vararg
関数が可変個の引数を取ることを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[vararg]  
  
```  
  
## <a name="remarks"></a>コメント  
 **Vararg** C++ 属性と同じ機能を持つ、 [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304) MIDL 属性。  
  
## <a name="example"></a>例  
 次のコードは、の使い方を示しています**vararg**:。  
  
```  
// cpp_attr_ref_vararg.cpp  
// compile with: /LD  
#include "unknwn.h"  
#include "oaidl.h"  
[module(name="MyLibrary")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface X : public IUnknown   
{  
   [vararg] HRESULT Button([in, satype(VARIANT)]SAFEARRAY *psa);  
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイス メソッド|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [メソッド属性](../windows/method-attributes.md)   
