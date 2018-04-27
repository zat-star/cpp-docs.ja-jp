---
title: shuffle_order_engine クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- random/std::shuffle_order_engine
- random/std::shuffle_order_engine::base
- random/std::shuffle_order_engine::discard
- random/std::shuffle_order_engine::operator()
- random/std::shuffle_order_engine::base_type
- random/std::shuffle_order_engine::seed
dev_langs:
- C++
helpviewer_keywords:
- std::shuffle_order_engine [C++]
- std::shuffle_order_engine [C++], base
- std::shuffle_order_engine [C++], discard
- std::shuffle_order_engine [C++], base_type
- std::shuffle_order_engine [C++], seed
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6f5d62394a4955e11b31b4d0b3c134cd0840d3e5
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="shuffleorderengine-class"></a>shuffle_order_engine クラス

ベースのエンジンから返された値を並べ替えることで、ランダム シーケンスを生成します。

## <a name="syntax"></a>構文

```cpp
template <class Engine, size_t K>
class shuffle_order_engine;
```

### <a name="parameters"></a>パラメーター

`Engine` ベース エンジンの種類。

`K` **テーブル サイズ**です。 バッファー (テーブル) 内の要素の数。 **前提条件**: `0 < K`

## <a name="members"></a>メンバー

||||
|-|-|-|
|`shuffle_order_engine::shuffle_order_engine`|`shuffle_order_engine::base`|`shuffle_order_engine::discard`|
|`shuffle_order_engine::operator()`|`shuffle_order_engine::base_type`|`shuffle_order_engine::seed`|

エンジンのメンバーの詳細については、[\<random>](../standard-library/random.md) をご覧ください。

## <a name="remarks"></a>コメント

このテンプレート クラスは、ベースのエンジンによって返される値を並べ替えることで値を生成する*エンジン アダプター*を表します。 各コンストラクターは、ベースのエンジンによって返される `K` 個の値を内部テーブルに読み込みます。値が要求されると、テーブルからランダムに要素が選択されます。

## <a name="requirements"></a>要件

**ヘッダー:** \<random>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<random>](../standard-library/random.md)<br/>
