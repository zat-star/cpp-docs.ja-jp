---
title: "ローカル (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.local
dev_langs:
- C++
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3543adfe0cb25f7946e6ed6c81c4bd66a7b60324
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="local-c"></a>local (C++)
インターフェイスのヘッダーで使用する場合を使用すると、ヘッダー ジェネレーターとして MIDL コンパイラを使用できます。 個々 の関数で使用する場合は、対象のスタブが生成されないローカル プロシージャを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[local]  
  
```  
  
## <a name="remarks"></a>コメント  
 `local` C++ 属性と同じ機能を持つ、[ローカル](http://msdn.microsoft.com/library/windows/desktop/aa367071)MIDL 属性。  
  
## <a name="example"></a>例  
 参照してください[call_as](../windows/call-as.md)の使用方法の例については`local`します。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`interface`、インターフェイス メソッド|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|**dispinterface**|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
 [メソッドの属性](../windows/method-attributes.md)   
 [call_as](../windows/call-as.md)   
