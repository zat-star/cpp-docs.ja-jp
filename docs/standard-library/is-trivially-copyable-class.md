---
title: is_trivially_copyable クラス | Microsoft Docs
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
- type_traits/std::is_trivially_copyable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2e2792c93b477c6d6aac4350045a506eda206eb
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallycopyable-class"></a>is_trivially_copyable クラス

型が自明にコピー可能な型であるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_trivially_copyable;
```

### <a name="parameters"></a>パラメーター

`T` 照会する型。

## <a name="remarks"></a>コメント

型述語のインスタンスは、型 `T` が自明にコピー可能な型である場合 true を保持し、それ以外の場合は false を保持します。 自明にコピー可能な型とは、自明でないコピー操作、移動操作、デストラクターが含まれない型のことです。 通常、ビット単位のコピーとして実装可能なコピー操作は自明であるとみなされます。 組み込みの型と自明にコピー可能な型の配列は、両方とも自明にコピー可能です。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
