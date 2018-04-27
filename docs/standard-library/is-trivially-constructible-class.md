---
title: is_trivially_constructible クラス | Microsoft Docs
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
- type_traits/std::is_trivially_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f564ae5970f56690f493e26cbefebbdc34cfec61
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallyconstructible-class"></a>is_trivially_constructible クラス

指定した引数型の使用時に型を自明に構築できるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>パラメーター

`T` 照会する型。

`Args` 引数の型のコンス トラクターで一致するように`T`です。

## <a name="remarks"></a>コメント

型述語のインスタンスは、型 `T` が `Args` の引数型を使用して自明に構築可能な場合 true を保持します。それ以外の場合は false を保持します。 型 `T` が自明に構築可能であるのは、変数定義 `T t(std::declval<Args>()...);` の形式が適切であり、自明ではない操作を呼び出さないことがわかっている場合です。 `T` と `Args` のすべての型はともに、完全な型、`void`、または不明なバインドの配列にする必要があります。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
