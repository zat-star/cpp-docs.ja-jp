---
title: '&lt;bitset&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- <bitset>
dev_langs:
- C++
helpviewer_keywords:
- <bitset> header
- bitset header
ms.assetid: af30a9b9-489e-46e3-9d29-5f3ea07ae6dc
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 71b2f2d8c12c2d82b1e2a2ba2c68f061ce518658
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="ltbitsetgt"></a>&lt;bitset&gt;

ビットの固定サイズ シーケンスを表して処理するための、テンプレート クラス ビットセットと 2 つのサポート テンプレート関数を定義します。

## <a name="syntax"></a>構文

```

#include <bitset>

```

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator&](../standard-library/bitset-operators.md#op_amp)|次の 2 つのビットセット間でビットごとの AND を実行します。|
|[operator<\<](../standard-library/bitset-operators.md#op_lt_lt)|ビット シーケンスのテキスト表現を標準出力ストリームに挿入します。|
|[operator>>](../standard-library/bitset-operators.md#op_gt_gt)|ビット シーケンスのテキスト表現を標準入力ストリームに挿入します。|
|[operator^](../standard-library/bitset-operators.md#op_xor)|次の 2 つのビットセット間でビットごとの EXCLUSIVE-OR を実行します。|
|[operator&#124;](../standard-library/bitset-operators.md#op_or)|次の 2 つのビットセット間でビットごとの OR を実行します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[bitset クラス](../standard-library/bitset-class.md)|このテンプレート クラスは、固定数のビットで構成されるシーケンスを格納するオブジェクト型を記述します。これらのビットによって、一連の項目または条件のフラグを保持するためのコンパクトな方法が提供されます。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
