---
title: "pointer_default |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.pointer_default
dev_langs: C++
helpviewer_keywords: pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b55bf95c7abdffe8dd0a0e0071d86f06baad344e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="pointerdefault"></a>pointer_default
パラメーター リストに表示される最上位のポインターを除く、すべてのポインターの既定のポインターの属性を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ pointer_default(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *値*  
 ポインター型を記述する値: **ptr**、 `ref`、または**一意**です。  
  
## <a name="remarks"></a>コメント  
 **Pointer_default** C++ 属性と同じ機能を持つ、 [pointer_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) MIDL 属性。  
  
## <a name="example"></a>例  
 例を参照して[defaultvalue](../windows/defaultvalue.md)の使用例の**pointer_default**です。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`interface`|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
