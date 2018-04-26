---
title: '&lt;forward_list&gt; 系関数 | Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: 7b990c760a94589967d5e2020082cb1f48250dac
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="ltforwardlistgt-functions"></a>&lt;forward_list&gt; 系関数

||
|-|
|[swap](#swap)|

## <a name="swap"></a>  swap

2 つの前方リストの要素を交換します。

```cpp
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`left`|`forward_list` 型のオブジェクト。|
|`right`|`forward_list` 型のオブジェクト。|

### <a name="remarks"></a>コメント

このテンプレート関数は、`left.swap(right)` を実行します。

## <a name="see-also"></a>関連項目

[<forward_list>](../standard-library/forward-list.md)<br/>
