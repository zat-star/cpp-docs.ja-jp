---
title: '&lt;new&gt; typedefs | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
caps.latest.revision: 7
manager: ghogen
ms.openlocfilehash: 53a13168986171d3240cc15e405fc08b3db07e96
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt; typedefs

||
|-|
|[new_handler](#new_handler)|

## <a name="new_handler"></a>  new_handler

新しいハンドラーとして使用するのに適した関数を指す型。

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>コメント

このハンドラー関数の型は、追加の記憶域の要求を満たすことができない場合に、**operatornew** または `operator new[]` によって呼び出されます。

### <a name="example"></a>例

`new_handler` を戻り値として使用する例については、「[set_new_handler](../standard-library/new-functions.md#set_new_handler)」をご覧ください。

## <a name="see-also"></a>関連項目

[\<new>](../standard-library/new.md)<br/>
