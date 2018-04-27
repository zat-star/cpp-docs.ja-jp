---
title: money_base クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xlocmon/std::money_base
dev_langs:
- C++
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a33e60ff54c7ec03ef806f5104513c9838449190
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="moneybase-class"></a>money_base クラス

このクラスは、テンプレート クラス [moneypunct](../standard-library/moneypunct-class.md) のすべての特殊化に共通する列挙型および構造体を表します。

## <a name="syntax"></a>構文

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>コメント

列挙型 **part** は、構造パターンの配列フィールドの要素で使用可能な値を表します。 **part** の値は次のとおりです。

- **none**: 0 個以上の空白に一致するか、何も生成しません。

- **sign**: 正の記号または負の記号に一致するか、正の記号または負の記号を生成します。

- **space**: 0 個以上の空白に一致するか、1 個の空白を生成します。

- **symbol**: 通貨記号に一致するか、通貨記号を生成します。

- **value**: 通貨の値に一致するか、通貨の値を生成します。

## <a name="requirements"></a>要件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
