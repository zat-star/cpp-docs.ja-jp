---
title: '&lt;memory&gt; 列挙型 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: 035175b2fea506fa341e260f042ae426e85421e4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt; 列挙型

||
|-|
|[pointer_safety](#pointer_safety)|

## <a name="pointer_safety"></a>  pointer_safety 列挙型

`get_pointer_safety` によって返される可能性がある値の列挙型です。

class pointer_safety { relaxed, preferred, strict };

### <a name="remarks"></a>コメント

スコープを持つ `enum` が、`get_pointer_safety()` によって返される以下の値を定義します。

`relaxed` -- 安全に派生していないポインター (明らかに、宣言されたオブジェクトまたは割り当てられたオブジェクトへのポインター) が、安全に派生したポインターと同じように扱われます。

`preferred` -- 上と同様ですが、安全に派生していないポインターを逆参照することはできません。

`strict` -- 安全に派生していないポインターは、安全に派生したポインターとは異なる方法で扱われる場合があります。

## <a name="see-also"></a>関連項目

[\<memory>](../standard-library/memory.md)<br/>
