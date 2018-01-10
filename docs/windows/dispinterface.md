---
title: "dispinterface |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.dispinterface
dev_langs: C++
helpviewer_keywords: dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf7fb54b4059bc56aea967f03b9e4c2874f84e82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="dispinterface"></a>dispinterface
ディスパッチ インターフェイスとしてインターフェイスを .idl ファイルに配置します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[dispinterface]  
  
```  
  
## <a name="remarks"></a>コメント  
 **dispinterface** C++ 属性がインターフェイスの前にあると、インターフェイスは生成される .idl ファイルのライブラリ ブロック内に配置されます。  
  
 基底クラスを指定しないと、ディスパッチ インターフェイスは `IDispatch`から派生します。 ディスパッチ インターフェイスのメンバーの [id](../windows/id.md) を指定する必要があります。  
  
 MIDL のドキュメントには [dispinterface](http://msdn.microsoft.com/library/windows/desktop/aa366802) の次のような使用例があります。  
  
```  
dispinterface helloPro   
   { interface hello; };   
```  
  
 これは、 **dispinterface** 属性の有効な使用方法ではありません。  
  
## <a name="example"></a>例  
 [dispinterface](../windows/bindable.md) の使用方法の例については、 **bindable**の例を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`interface`|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|**dual**、 **object**、 **oleautomation**、 `local`、 **ms_union**|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [使用して属性](../windows/attributes-by-usage.md)   
 [uuid](../windows/uuid-cpp-attributes.md)   
 [デュアル](../windows/dual.md)   
 [カスタム](../windows/custom-cpp.md)   
 [object](../windows/object-cpp.md)   
 [__interface](../cpp/interface.md)   
