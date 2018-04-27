---
title: time_base クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- locale/std::time_base
dev_langs:
- C++
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c2bb249399d844aec74e53b12b9db046a2783a6
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="timebase-class"></a>time_base クラス

このクラスは、time_get テンプレート クラスのファセットの基底クラスとして使用されます。**dateorder** 列挙型とこの型の複数の定数のみを定義します。

## <a name="syntax"></a>構文

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {no_order,
    dmy,
 mdy,
    ymd,
 ydm};
    time_base(
 size_t _Refs = 0)
 ~time_base();

};
```

## <a name="remarks"></a>コメント

各定数は、日付部分を順序付けるための異なる方法を特徴付けます。 定数は次のとおりです。

- **no_order** は、特定の順序を指定しません。

- **dmy** は、2 December 1979 のように日、月、年という順序を指定します。

- **dmy** は、December 2, 1979 のように、月、日、年という順序を指定します。

- **ymd** は、1979/12/2 のように、年、月、日という順序を指定します。

- **ymd** は、1979: 2 Dec のように、年、日、月という順序を指定します。

## <a name="requirements"></a>要件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
