---
title: '&lt;ostream&gt; typedef | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: 8c451b16a581ab13f87c7bcca793efe3a0f07bf5
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; typedef

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

`char` に対して特殊化された basic_ostream と `char` に対して特殊化された `char_traits` に基づいて型を作成します。

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>コメント

この型はテンプレート クラス [basic_ostream](../standard-library/basic-ostream-class.md) の同意語であり、既定の特性を持つ型 `char` の要素に対して特殊化されています。

## <a name="wostream"></a>  wostream

`wchar_t` に対して特殊化された basic_ostream と `wchar_t` に対して特殊化された `char_traits` に基づいて型を作成します。

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>コメント

この型はテンプレート クラス [basic_ostream](../standard-library/basic-ostream-class.md) の同意語であり、既定の特性を持つ型 `wchar_t` の要素に対して特殊化されています。

## <a name="see-also"></a>関連項目

[\<ostream>](../standard-library/ostream.md)<br/>
