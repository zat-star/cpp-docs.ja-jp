---
title: hash 構造体 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- typeindex/std::hash
dev_langs:
- C++
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ef813287b8183e4d59e1d6af15c997eab6f8cbc4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="hash-structure"></a>hash 構造体

テンプレート クラスは `val.hash_code()` を返すようにメソッドを定義します。 メソッドは、ハッシュ関数を定義します。これは [type_index](../standard-library/type-index-class.md) 型の値をインデックス値の分布にマッピングするために使用されます。

## <a name="syntax"></a>構文

```cpp
template <>
struct hash<type_index>
: public unary_function<type_index, size_t>
 { // hashes a typeinfo object
    size_t operator()(type_index val) const;

};
```

## <a name="see-also"></a>関連項目

[\<typeindex>](../standard-library/typeindex.md)<br/>
