---
title: "is_move_constructible クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 15c1fb9b3b4e3dc27b887ac70005be55813399a7
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
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
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)



