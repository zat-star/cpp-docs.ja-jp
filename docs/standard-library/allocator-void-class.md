---
title: allocator&lt;void&gt; クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
dev_langs:
- C++
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1bc3128b81aa1ea10c1c147d1d1c1f7d5bb8550
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="allocatorltvoidgt-class"></a>allocator&lt;void&gt; クラス

`void` 型へのテンプレート クラスのアロケーターを特殊化し、このコンテキストで意味を持つ型を定義します。

## <a name="syntax"></a>構文

```cpp
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```

## <a name="remarks"></a>コメント

このクラスは、*void* 型のテンプレート クラス [allocator](../standard-library/allocator-class.md) を明示的に特殊化します。 コンストラクターと代入演算子の動作は、同じテンプレート クラスの動作と同じですが、次の型のみを定義します。

- [const_pointer](../standard-library/allocator-class.md#const_pointer)

- [pointer](../standard-library/allocator-class.md#pointer)

- [value_type](../standard-library/allocator-class.md#value_type)

- [rebind](../standard-library/allocator-class.md#rebind)、入れ子になったテンプレート クラス

## <a name="requirements"></a>要件

**ヘッダー:** \<memory>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
