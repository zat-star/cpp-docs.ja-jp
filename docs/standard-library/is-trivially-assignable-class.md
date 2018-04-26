---
title: is_trivially_assignable クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_trivially_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b9ccc4937ec4f54756482fd8c3f7028506ca50d
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallyassignable-class"></a>is_trivially_assignable クラス

`From` 型の値を `To` 型に普通に代入できるかどうかをテストします

## <a name="syntax"></a>構文

```cpp
template <class To, class From>
struct is_trivially_assignable;
```

### <a name="parameters"></a>パラメーター

オブジェクトの型には、割り当てを受け取る。

値を提供するオブジェクトの型。

## <a name="remarks"></a>コメント

式 `declval<To>() = declval<From>()` は正しい形式である必要があり、トリビアルでない演算を必要としないことがコンパイラに判明している必要があります。 `From` と `To` の両方とも完全な型、`void`、または不明なバインドの配列にする必要があります。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
