---
title: sync_per_container クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
dev_langs:
- C++
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d917fcae71f5e3c152082e4ecdac27626f6637f7
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="syncpercontainer-class"></a>sync_per_container クラス

アロケーター オブジェクトごとに個別のキャッシュ オブジェクトを提供する[同期フィルター](../standard-library/allocators-header.md)を記述します。

## <a name="syntax"></a>構文

```cpp
template <class Cache>
class sync_per_container
 : public Cache
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`Cache`|同期フィルターに関連付けられているキャッシュの型。 これは、[cache_chunklist](../standard-library/cache-chunklist-class.md)、[cache_freelist](../standard-library/cache-freelist-class.md)、[cache_suballoc](../standard-library/cache-suballoc-class.md) のいずれかです。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[equals](#equals)|2 つのキャッシュが等しいかどうかを比較します。|

## <a name="requirements"></a>要件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="equals"></a>  sync_per_container::equals

2 つのキャッシュが等しいかどうかを比較します。

```cpp
bool equals(const sync_per_container<Cache>& Other) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`Cache`|同期フィルターのキャッシュ オブジェクト。|
|`Other`|等しいかどうかを比較するキャッシュ オブジェクト。|

### <a name="return-value"></a>戻り値

このメンバー関数は常に `false` を返します。

### <a name="remarks"></a>コメント

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)<br/>
