---
title: is_error_code_enum 構造体 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- future/std::is_error_code_enum
dev_langs:
- C++
ms.assetid: 84ae4b99-66d2-41ba-9b50-645fcbe14630
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e0bac7971a224655f6fd218df5e3a9256569820
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="iserrorcodeenum-structure"></a>is_error_code_enum 構造体

[future_errc](../standard-library/future-enums.md#future_errc) が [error_code](../standard-library/error-code-class.md) の格納に適していることを示す特殊化です。

## <a name="syntax"></a>構文

```cpp
template <>
struct is_error_code_enum<Future_errc> : public true_type;
```

## <a name="requirements"></a>要件

**ヘッダー:** \<将来 >

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<future>](../standard-library/future.md)<br/>
