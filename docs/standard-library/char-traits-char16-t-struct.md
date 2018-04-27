---
title: char_traits&lt;char16_t&gt; 構造体 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- char_traits<char16_t>
- iosfwd/std::char_traits<char16_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<char16_t> class
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b76839dee5df211331f10f11e20ab9a45a2f4eeb
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="chartraitsltchar16tgt-struct"></a>char_traits&lt;char16_t&gt; 構造体

テンプレート構造体 **char_traits\<CharType>** を `char16_t` 型の要素に特殊化した構造体。

## <a name="syntax"></a>構文

```cpp
template <>
struct char_traits<char16_t>;
```

## <a name="remarks"></a>コメント

特殊化により、構造体で型 `char16_t` のオブジェクトを操作するライブラリ関数を利用できます。

## <a name="requirements"></a>要件

**ヘッダー:** \<string>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<string>](../standard-library/string.md)<br/>
[char_traits 構造体](../standard-library/char-traits-struct.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
