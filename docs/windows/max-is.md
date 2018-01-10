---
title: "max_is |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.max_is
dev_langs: C++
helpviewer_keywords: max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d43ed06797ed79942a43612ab4c9ae774c4fcf17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="maxis"></a>max_is
有効な配列インデックスの最大値を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ max_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *式*  
 1 つ以上の C 言語の式。 空の引数スロットを指定します。  
  
## <a name="remarks"></a>コメント  
 **Max_is** C++ 属性と同じ機能を持つ、 [max_is](http://msdn.microsoft.com/library/windows/desktop/aa367074) MIDL 属性。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|フィールドに`struct`または**共用体**パラメーターをインターフェイスでは、インターフェイス メソッド|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|**size_is**|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="example"></a>例  
 参照してください[first_is](../windows/first-is.md)配列のセクションを指定する方法の例についてはします。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [パラメーター属性](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [last_is](../windows/last-is.md)   
 [length_is](../windows/length-is.md)   
 [size_is](../windows/size-is.md)   
