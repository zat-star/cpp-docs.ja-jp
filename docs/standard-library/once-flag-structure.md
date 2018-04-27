---
title: once_flag 構造体 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- mutex/std::once_flag
dev_langs:
- C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 249207d8723318c1a11760c512f3b88f13c97266
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="onceflag-structure"></a>once_flag 構造体

テンプレート関数 [call_once](../standard-library/mutex-functions.md#call_once) で使用する `struct` を表し、実行する複数スレッドがある場合でも、初期化コードが 1 回だけ呼び出されるようにします。

## <a name="syntax"></a>構文

struct once_flag { constexpr once_flag() noexcept; once_flag(const once_flag&); once_flag& operator=(const once_flag&); };

## <a name="remarks"></a>コメント

`once_flag` `struct`既定のコンス トラクターのみです。

`once_flag` 型のオブジェクトは、作成することはできますがコピーはできません。

## <a name="requirements"></a>要件

**ヘッダー:** \<ミュー テックス >

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
