---
title: codecvt_base クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xlocale/std::codecvt_base
dev_langs:
- C++
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5fbe4d0c6789ada5979359d0498b95350c5ba0c3
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="codecvtbase-class"></a>codecvt_base クラス

変換の結果を示すためにファセットのメンバー関数の戻り値の型として使用される、**result** と呼ばれる列挙型を定義するために使用される codecvt クラスの基底クラス。

## <a name="syntax"></a>構文

```cpp
class codecvt_base : public locale::facet {
public:
    enum result {ok, partial, error, noconv};
    codecvt_base( size_t _Refs = 0);
    bool always_noconv() const;
    int max_length() const;
    int encoding() const;
    ~codecvt_base()

protected:
    virtual bool do_always_noconv() const;
    virtual int do_max_length() const;
    virtual int do_encoding() const;
};
```

## <a name="remarks"></a>コメント

このクラスは、テンプレート クラス [codecvt](../standard-library/codecvt-class.md) のすべての特殊化に共通する列挙型を表します。 列挙の結果には、次のような [do_in](../standard-library/codecvt-class.md#do_in) または [do_out](../standard-library/codecvt-class.md#do_out) からの可能な戻り値が示されます。

- 内部と外部の文字エンコーディングの変換が正常に行われた場合は、**ok**。

- 変換先が、変換を正常に行うのに十分な大きさでない場合は、**partial**。

- ソース シーケンスが無効な形式である場合は、**error**。

- 関数で変換が行われない場合は、**noconv**。

## <a name="requirements"></a>要件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
