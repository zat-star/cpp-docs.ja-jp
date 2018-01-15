---
title: "is_constructible クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_constructible
dev_langs: C++
helpviewer_keywords: is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a2d2127ec8f007dbf301fca7e01a59a7ef462cd1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="isconstructible-class"></a>is_constructible クラス
指定した引数型の使用時に型を構築できるかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, class... Args>  
struct is_constructible;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 照会する型。  
  
 `Args`  
 `T` のコンストラクター内の一致させる引数型。  
  
## <a name="remarks"></a>コメント  
 型述語のインスタンスは、型 `T` が `Args` の引数型を使用して構築可能な場合 true を保持します。それ以外の場合は false を保持します。 型 `T` を構築できるのは、変数定義 `T t(std::declval<Args>()...);` の形式が適切である場合です。 `T` と `Args` のすべての型は両方とも、完全な型、`void`、または不明なバインドの配列にする必要があります。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)



