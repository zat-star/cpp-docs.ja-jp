---
title: "usesgetlasterror |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05c74f1254230270654b3dc0b44f541e4fe9ef2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="usesgetlasterror"></a>usesgetlasterror
呼び出し元に通知する関数を呼び出すときにエラーがある場合、呼び出し元は、ことができますし、`GetLastError`エラー コードを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[usesgetlasterror]  
  
```  
  
## <a name="remarks"></a>コメント  
 **Usesgetlasterror** C++ 属性と同じ機能を持つ、 [usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) MIDL 属性。  
  
## <a name="example"></a>例  
 参照してください、 [idl_module](../windows/idl-module.md)を使用する方法のサンプルについては例**usesgetlasterror**です。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**モジュール**属性|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
