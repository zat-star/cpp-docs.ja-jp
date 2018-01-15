---
title: "helpfile |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.helpfile
dev_langs: C++
helpviewer_keywords: helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 63987b4e1427f12925b55fa3570d80b9e3a4686d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="helpfile"></a>helpfile
タイプ ライブラリのヘルプ ファイルの名前を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ helpfile(  
   "filename"  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *ファイル名*  
 ヘルプ トピックが含まれているファイルの名前。  
  
## <a name="remarks"></a>コメント  
 **Helpfile** C++ 属性と同じ機能を持つ、 [helpfile](http://msdn.microsoft.com/library/windows/desktop/aa366853) MIDL 属性。  
  
## <a name="example"></a>例  
 例を参照して[モジュール](../windows/module-cpp.md)の使用方法の例については**helpfile**です。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`interface`、 `typedef`、**クラス**、メソッド、プロパティ|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [メソッドの属性](../windows/method-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [helpcontext](../windows/helpcontext.md)   
 [helpstring](../windows/helpstring.md)   
