---
title: '&lt;typeindex&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- <typeindex>
dev_langs:
- C++
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 63eae51554003a2c12caf2522a912adc9b96ec02
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="lttypeindexgt"></a>&lt;typeindex&gt;

[type_info](../cpp/type-info-class.md) クラスのオブジェクトのインデックス作成をサポートするクラスや関数を定義するには、標準ヘッダー \<typeindex> をインクルードします。

## <a name="syntax"></a>構文

```cpp
#include <typeindex>
```

## <a name="remarks"></a>コメント

インデックス値の分布への [type_index](../standard-library/type-index-class.md) 型の値のマッピングに適した `hash function` は、[hash 構造体](../standard-library/hash-structure.md)で定義します。

`type_index` クラスは、インデックス作成をしやすくするために `type_info` オブジェクトへのポインターをラップするものです。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
