---
title: "オブジェクト (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.object
dev_langs: C++
helpviewer_keywords: object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 75694398f01cdf790b292d53aff5466b1e27a919
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="object-c"></a>object (C++)
カスタムのインターフェイスを識別します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[object]  
  
```  
  
## <a name="remarks"></a>コメント  
 インターフェイス定義の直前、**オブジェクト**C++ 属性により、インターフェイス、カスタム インターフェイスとして .idl ファイル内に配置されます。  
  
 オブジェクトでマークされた任意のインターフェイスを継承する必要があります**IUnknown**です。 継承の基本インターフェイスのいずれかの場合、この条件が満たされる**IUnknown**です。 基本インターフェイスを継承できない場合**IUnknown**、コンパイラでマークされたインターフェイスと、**オブジェクト**から派生する**IUnknown**です。  
  
## <a name="example"></a>例  
 参照してください[nonbrowsable](../windows/nonbrowsable.md)の使用方法の例については**オブジェクト**です。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`interface`|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
 [デュアル](../windows/dual.md)   
 [ディスパッチ インターフェイス](../windows/dispinterface.md)   
 [カスタム](../windows/custom-cpp.md)   
 [__interface](../cpp/interface.md)   
