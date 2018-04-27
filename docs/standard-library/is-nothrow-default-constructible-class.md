---
title: is_nothrow_default_constructible クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_default_constructible
ms.assetid: c576fcc9-5be1-43aa-b93a-64d3f1848887
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f5736237b0111180016375033e505ecc798677b
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="isnothrowdefaultconstructible-class"></a>is_nothrow_default_constructible クラス

スローしない既定コンストラクターが型に存在するかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_nothrow_default_constructible;
```

### <a name="parameters"></a>パラメーター

`Ty` 照会する型。

## <a name="remarks"></a>コメント

スローしない既定コンストラクターが型 `Ty` に存在する場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。 型述語のインスタンスは `is_nothrow_constructible<Ty>` と同じです。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
