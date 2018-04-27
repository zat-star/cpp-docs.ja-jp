---
title: is_error_condition_enum クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- system_error/std::is_error_condition_enum
dev_langs:
- C++
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 43959823df01187961fbb9e113160b026e4d31d4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="iserrorconditionenum-class"></a>is_error_condition_enum クラス

[error_condition](../standard-library/error-condition-class.md) をテストする型述語を表します。

## <a name="syntax"></a>構文

```cpp
template <_Enum>
class is_error_condition_enum;
```

## <a name="remarks"></a>コメント

型 `_Enum` が型 `error_condition` のオブジェクトを格納するのに適した列挙型の値である場合、この[型述語](../standard-library/type-traits.md)のインスタンスは true を保持します。

ユーザー定義型のこの型に特殊化を追加できます。

## <a name="requirements"></a>要件

**ヘッダー:** \<system_error>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[<system_error>](../standard-library/system-error.md)<br/>
