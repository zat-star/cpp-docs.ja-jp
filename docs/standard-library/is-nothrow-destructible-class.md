---
title: is_nothrow_destructible クラス | Microsoft Docs
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
- type_traits/std::is_nothrow_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_destructible
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 14a28261ee1d5e3e58cc36e6adf0ac1da08b1b28
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="isnothrowdestructible-class"></a>is_nothrow_destructible クラス

型が破棄可能で、デストラクタ―がスローしないとコンパイラに判明しているかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_nothrow_destructible;
```

### <a name="parameters"></a>パラメーター

`T` 照会する型。

## <a name="remarks"></a>コメント

型 `T` が破棄可能な型で、デストラクタ―がスローしないとコンパイラに判明している場合、型述語のインスタンスは true を保持します。 それ以外の場合、false を保持します。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
