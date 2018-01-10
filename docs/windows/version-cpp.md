---
title: "バージョン (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.version
dev_langs: C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db6c31df932890799f68e2ae466b0a927f0f999f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="version-c"></a>version (C++)
クラスの複数のバージョン間で特定のバージョンを識別します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ version(  
   "version"  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *version*  
 コクラスのバージョン番号。 指定しない場合、1.0 は .idl ファイルに配置されます。  
  
## <a name="remarks"></a>コメント  
 **バージョン**C++ 属性と同じ機能を持つ、[バージョン](http://msdn.microsoft.com/library/windows/desktop/aa367306)MIDL 属性が生成された .idl ファイルに渡されます。  
  
## <a name="example"></a>例  
 参照してください、[バインド可能な](../windows/bindable.md)のサンプルの使用例**バージョン**します。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`|  
|**反復可能**|×|  
|**必要な属性**|**coclass**|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [コンパイラ属性](../windows/compiler-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
