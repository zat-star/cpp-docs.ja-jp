---
title: '&lt;thread&gt; 演算子 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- thread/std::operator!=
- thread/std::operator&gt;
- thread/std::operator&gt;=
- thread/std::operator&lt;
- thread/std::operator&lt;&lt;
- thread/std::operator&lt;=
- thread/std::operator==
dev_langs:
- C++
ms.assetid: e6bb6c0f-64f9-4cb2-9ff2-05b88a6ba7ac
caps.latest.revision: 11
manager: ghogen
helpviewer_keywords:
- std::operator!= (thread)
- std::operator&gt; (thread)
- std::operator&gt;= (thread)
- std::operator&lt; (thread)
- std::operator&lt;&lt; (thread)
- std::operator&lt;= (thread)
- std::operator== (thread)
ms.openlocfilehash: 58c690b51d51a75b644430aaf4e5b3eeb672ae5a
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="ltthreadgt-operators"></a>&lt;thread&gt; 演算子

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|

## <a name="op_gt_eq"></a>  演算子&gt;=

一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値以上かどうかを判断します。

```cpp
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

`Left` 左側の`thread::id`オブジェクト。

`Right` 右側の`thread::id`オブジェクト。

### <a name="return-value"></a>戻り値

`!(Left < Right)`

### <a name="remarks"></a>コメント

この関数では、例外がスローされません。

## <a name="op_gt"></a>  operator&gt;

一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値より大きいかどうかを判断します。

```cpp
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

`Left` 左側の`thread::id`オブジェクト。

`Right` 右側の`thread::id`オブジェクト。

### <a name="return-value"></a>戻り値

`Right < Left`

### <a name="remarks"></a>コメント

この関数では、例外がスローされません。

## <a name="op_lt_eq"></a>  演算子&lt;=

一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値以下かどうかを判断します。

```cpp
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

`Left` 左側の`thread::id`オブジェクト。

`Right` 右側の`thread::id`オブジェクト。

### <a name="return-value"></a>戻り値

`!(Right < Left)`

### <a name="remarks"></a>コメント

この関数では、例外がスローされません。

## <a name="op_lt"></a>  operator&lt;

一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値より小さいかどうかを判断します。

```cpp
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

`Left` 左側の`thread::id`オブジェクト。

`Right` 右側の`thread::id`オブジェクト。

### <a name="return-value"></a>戻り値

全体の順序付けの中で `Left` が `Right` よりも前にある場合は `true`、それ以外の場合は `false`。

### <a name="remarks"></a>コメント

この演算子は、すべての `thread::id` オブジェクトでの全体の順序付けを定義します。 これらのオブジェクトは、連想コンテナー内のキーとして使用できます。

この関数では、例外がスローされません。

## <a name="op_neq"></a>  operator!=

2 つの `thread::id` オブジェクトが等しくないかどうかを比較します。

```cpp
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

`Left` 左側の`thread::id`オブジェクト。

`Right` 右側の`thread::id`オブジェクト。

### <a name="return-value"></a>戻り値

`!(Left == Right)`

### <a name="remarks"></a>コメント

この関数では、例外がスローされません。

## <a name="op_eq_eq"></a>  operator==

2 つの `thread::id` オブジェクトが等しいかどうかを比較します。

```cpp
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

`Left` 左側の`thread::id`オブジェクト。

`Right` 右側の`thread::id`オブジェクト。

### <a name="return-value"></a>戻り値

2 つのオブジェクトが同じ実行スレッドを表している場合、またはいずれのオブジェクトも実行スレッドを表していない場合は `true`、それ以外の場合は `false`。

### <a name="remarks"></a>コメント

この関数では、例外がスローされません。

## <a name="op_lt_lt"></a>  演算子&lt;&lt;

`thread::id` オブジェクトのテキスト表現をストリームに挿入します。

```cpp
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```

### <a name="parameters"></a>パラメーター

`Ostr` A [basic_ostream](../standard-library/basic-ostream-class.md)オブジェクト。

`Id` A`thread::id`オブジェクト。

### <a name="return-value"></a>戻り値

`Ostr`。

### <a name="remarks"></a>コメント

この関数は、`Ostr` に `Id` を挿入します。

2 つの `thread::id` オブジェクトが等しい場合、これらのオブジェクトの挿入されたテキスト表現は同じです。

## <a name="see-also"></a>関連項目

[\<thread>](../standard-library/thread.md)<br/>
