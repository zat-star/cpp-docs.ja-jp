---
title: "last_is |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.last_is
dev_langs: C++
helpviewer_keywords: last_is attribute
ms.assetid: 9e045ac0-fa38-4249-af55-67bde5d0a58c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d7a230299a94ba33a142ca44ebc34981f7201ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="lastis"></a>last_is
転送する最後の配列要素のインデックスを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ last_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *式*  
 1 つ以上の C 言語の式。 空の引数スロットを指定します。  
  
## <a name="remarks"></a>コメント  
 **Last_is** C++ 属性と同じ機能を持つ、 [last_is](http://msdn.microsoft.com/library/windows/desktop/aa367066) MIDL 属性。  
  
## <a name="example"></a>例  
 参照してください[first_is](../windows/first-is.md)配列のセクションを指定する方法の例についてはします。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|フィールドに`struct`または**共用体**パラメーターをインターフェイスでは、インターフェイス メソッド|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [パラメーター属性](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [max_is](../windows/max-is.md)   
 [length_is](../windows/length-is.md)   
 [size_is](../windows/size-is.md)   
