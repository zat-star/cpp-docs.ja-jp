---
title: "カスタム (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.custom
dev_langs: C++
helpviewer_keywords: custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e55fd4ad47470a86a0a3d61cc847c20fb21768e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="custom-c"></a>custom (C++)
タイプ ライブラリのオブジェクトのメタデータを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ custom(  
   uuid,   
   value  
) ];  
```  
  
#### <a name="parameters"></a>パラメーター  
 *uuid*  
 一意の ID。  
  
 *値*  
 バリアントを入れる値。  
  
## <a name="remarks"></a>コメント  
 **カスタム**C++ 属性を使用すると、タイプ ライブラリに配置される情報がします。 ツールをタイプ ライブラリからカスタムの値を読み取る必要があります。  
  
 **カスタム**属性と同じ機能を持つ、[カスタム](http://msdn.microsoft.com/library/windows/desktop/aa366766)MIDL 属性。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|非 COM `interface`、**クラス**、 `enum`s、`idl_module`メソッド、インターフェイスのメンバー、インターフェイスのパラメーター、 `typedef`s、**共用体**s、 `struct`s|  
|**反復可能**|[はい]|  
|**必要な属性**|**コクラス**(クラスを使用) する場合|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [スタンドアロン属性](../windows/stand-alone-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [パラメーター属性](../windows/parameter-attributes.md)   
 [メソッドの属性](../windows/method-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
