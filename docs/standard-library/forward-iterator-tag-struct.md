---
title: forward_iterator_tag 構造体 | Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xutility/std::forward_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2fa9e405162f0ed56866a5c8e15d894010396e1
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="forwarditeratortag-struct"></a>forward_iterator_tag 構造体

前方反復子を表す **iterator_category** 関数の戻り値の型を提供するクラス。

## <a name="syntax"></a>構文

```cpp
struct forward_iterator_tag    : public input_iterator_tag {};
```

## <a name="remarks"></a>コメント

カテゴリ タグ クラスはアルゴリズムの選択にコンパイル タグとして使用されます。 テンプレート関数は、コンパイル時に最も効率的なアルゴリズムを利用できるように、その反復子引数の最も具体的なカテゴリを見つける必要があります。 型 `Iterator` の反復子ごとに、反復子の動作を表す最も具体的なカテゴリ タグとして `iterator_traits`< `Iterator`> **::iterator_category** を定義する必要があります。

この型は、**Iter** が前方反復子としてサービスを提供するオブジェクトを表すとき、**iterator**\< **Iter**> **::iterator_category** と同じになります。

## <a name="example"></a>例

**iterator_tags** の使用方法の例については、「[iterator_traits](../standard-library/iterator-traits-struct.md)」または 「[random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** \<iterator>

**名前空間:** std

## <a name="see-also"></a>関連項目

[input_iterator_tag 構造体](../standard-library/input-iterator-tag-struct.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
