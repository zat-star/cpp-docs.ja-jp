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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 8d5af1b1115d2845fcfa4dbd89dc3776e7e66ccf
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

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




