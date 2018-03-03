---
title: "retval |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.retval
dev_langs:
- C++
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf7aa0cf8dd9767f603807ee18e23fe02d3446c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="retval"></a>retval
メンバーの戻り値を受け取るパラメーターを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[retval]  
  
```  
  
## <a name="remarks"></a>コメント  
 **Retval** C++ 属性と同じ機能を持つ、 [retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) MIDL 属性。  
  
 **retval**関数の宣言の最後の引数に表示する必要があります。  
  
## <a name="example"></a>例  
 例を参照して[バインド可能な](../windows/bindable.md)の使用例の**retval**です。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイスのパラメーター、インターフェイス メソッド|  
|**反復可能**|×|  
|**必要な属性**|**out**|  
|**無効な属性**|**in**|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [パラメーター属性](../windows/parameter-attributes.md)   
 [メソッド属性](../windows/method-attributes.md)   
