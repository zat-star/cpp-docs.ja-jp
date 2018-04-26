---
title: char_traits&lt;wchar_t&gt; 構造体 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f2b20b72bf92679395b19b2ad6b8ae68143bb6d
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="chartraitsltwchartgt-struct"></a>char_traits&lt;wchar_t&gt; 構造体

テンプレート構造体 **char_traits\<CharType>** を `wchar_t` 型の要素に特殊化したクラス。

## <a name="syntax"></a>構文

```cpp
template <>
struct char_traits<wchar_t>;
```

## <a name="remarks"></a>コメント

特殊化により、構造体でこの型 `wchar_t` のオブジェクトを操作するライブラリ関数を利用できます。

## <a name="requirements"></a>要件

**ヘッダー:** \<string>

**名前空間:** std

## <a name="see-also"></a>関連項目

[char_traits 構造体](../standard-library/char-traits-struct.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
