---
title: "helpstring |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.helpstring
dev_langs: C++
helpviewer_keywords: helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 27cf95f5017775fbf7a0315341cea19931f64068
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="helpstring"></a>helpstring
適用すると、要素の記述に使用される文字の文字列を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ helpstring(  
   "string"  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `string`  
 ヘルプ文字列のテキスト。  
  
## <a name="remarks"></a>コメント  
 **Helpstring** C++ 属性と同じ機能を持つ、 [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) MIDL 属性。  
  
## <a name="example"></a>例  
 例を参照して[defaultvalue](../windows/defaultvalue.md)の使用方法の例については**helpstring**です。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`interface`、 `typedef`、**クラス**、メソッド、プロパティ|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [メソッドの属性](../windows/method-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [ヘルプ ファイル](../windows/helpfile.md)   
 [helpcontext](../windows/helpcontext.md)   
