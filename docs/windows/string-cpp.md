---
title: "文字列 (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.string
dev_langs: C++
helpviewer_keywords: string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0293785b9552b2e5696b9334e81aebf44c3bc4b7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="string-c"></a>string (C++)
示します、1 次元`char`、 `wchar_t`、**バイト**(または同等の) このような配列へのポインターまたは配列を文字列として扱う必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
  
[string]  
  
```  
  
## <a name="remarks"></a>コメント  
 **文字列**C++ 属性と同じ機能を持つ、[文字列](http://msdn.microsoft.com/library/windows/desktop/aa367270)MIDL 属性。  
  
## <a name="example"></a>例  
 次のコードは、使用する方法を示しています**文字列**インターフェイスと typedef:。  
  
```  
// cpp_attr_ref_string.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export, string] typedef char a[21];  
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   [id(1)] HRESULT Method3([in, string] char *pC);  
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|配列または配列、インターフェイスのパラメーター、インターフェイス メソッドへのポインター|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [配列属性](../windows/array-attributes.md)   
 [export](../windows/export.md)   
