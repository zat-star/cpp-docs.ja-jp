---
title: "underlying_type クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- underlying_type
- std.underlying_type
- std::underlying_type
- type_traits/std::underlying_type
dev_langs:
- C++
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 95012fdeb3ac78d5e1cc76e03ed851a0b9701f5e
ms.lasthandoff: 02/24/2017

---
# <a name="underlyingtype-class"></a>underlying_type クラス
列挙型の基になる整数型を生成します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
struct underlying_type;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 変更する型。  
  
## <a name="remarks"></a>コメント  
 `T` が列挙型の場合、テンプレート クラスのメンバー typedef `type` は `T` の基になる整数型に名前を付けます。それ以外の場合はメンバー typedef `type` はありません。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)




