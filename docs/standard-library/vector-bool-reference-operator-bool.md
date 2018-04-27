---
title: vector&lt;bool&gt;::reference::operator bool | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- operatorbool
- vector<bool>::reference::operatorbool
- bool
- std::vector<bool>::reference::operatorbool
dev_langs:
- C++
helpviewer_keywords:
- BOOL operator
- reference::operator bool
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89a027f9c31b9779991ebaee80b4e9d1a97d8ff7
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="vectorltboolgtreferenceoperator-bool"></a>vector&lt;bool&gt;::reference::operator bool

`vector<bool>::reference` から `bool` への暗黙の変換を提供します。

## <a name="syntax"></a>構文

```cpp
operator bool() const;
```

## <a name="return-value"></a>戻り値

[vector\<bool>](../standard-library/vector-bool-class.md) オブジェクトの要素のブール値。

## <a name="remarks"></a>コメント

`vector<bool>` オブジェクトはこの演算子では変更できません。

## <a name="requirements"></a>要件

**ヘッダー:** \<vector>

**名前空間:** std

## <a name="see-also"></a>関連項目

[ベクター\<bool >:: クラスを参照](../standard-library/vector-bool-reference-class.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
