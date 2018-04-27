---
title: is_fundamental クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_fundamental
dev_langs:
- C++
helpviewer_keywords:
- is_fundamental class
- is_fundamental
ms.assetid: b84eee84-2fb2-4611-beaf-b384074d8b6a
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6457c0b6cf90534af2df9e25be3f6ebca9be2a2
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="isfundamental-class"></a>is_fundamental クラス

型が void であるか数値型であるかを調べます。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_fundamental;
```

### <a name="parameters"></a>パラメーター

`Ty` 照会する型。

## <a name="remarks"></a>コメント

型述語のインスタンスは、型 `Ty` が基本型、つまり、`void`、整数型、浮動小数点型、またはそのいずれかの `cv-qualified` 形式の場合は true を保持し、それ以外の場合は false を保持します。

## <a name="example"></a>例

```cpp
// std__type_traits__is_fundamental.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_fundamental<trivial> == " << std::boolalpha
        << std::is_fundamental<trivial>::value << std::endl;
    std::cout << "is_fundamental<int> == " << std::boolalpha
        << std::is_fundamental<int>::value << std::endl;
    std::cout << "is_fundamental<const float> == " << std::boolalpha
        << std::is_fundamental<const float>::value << std::endl;
    std::cout << "is_fundamental<void> == " << std::boolalpha
        << std::is_fundamental<void>::value << std::endl;

    return (0);
    }

```

```Output
is_fundamental<trivial> == false
is_fundamental<int> == true
is_fundamental<const float> == true
is_fundamental<void> == true
```

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_compound クラス](../standard-library/is-compound-class.md)<br/>
