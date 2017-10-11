---
title: "is_move_constructible クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 9498029f431b287312583f78effc5197fc097fd6
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="ismoveconstructible-class"></a>is_move_constructible クラス
型に移動コンストラクターが存在するかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
struct is_move_constructible;
```  
  
#### <a name="parameters"></a>パラメーター  
 T  
 評価される型  
  
## <a name="remarks"></a>コメント  
 型 `T` が移動操作によって構築できる場合に、true と評価される型述語です。 この述語は `is_constructible<T, T&&>` と同じです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)




