---
title: mem_fun_ref_t クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xfunctional/std::mem_fun_ref_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun_ref_t class
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eaf3a1d3e549122c6d407ec3ade3f5f68fc53f4a
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="memfunreft-class"></a>mem_fun_ref_t クラス

参照引数による初期化を行うときに、引数を使用しない **non_const** メンバー関数を単項関数オブジェクトとして呼び出せるようにするアダプター クラス。

## <a name="syntax"></a>構文

```cpp
template <class Result, class Type>
class mem_fun_ref_t : public unary_function<Type, Result> {
    explicit mem_fun_ref_t(
    Result (Type::* _Pm)());

    Result operator()(Type& left) const;

};
```

### <a name="parameters"></a>パラメーター

`_Pm` クラスのメンバー関数へのポインター**型**関数オブジェクトに変換します。

`left` オブジェクトを`_Pm`でメンバー関数が呼び出されます。

## <a name="return-value"></a>戻り値

適合可能な単項関数。

## <a name="remarks"></a>コメント

このテンプレート クラスは `_Pm` のコピーをプライベート メンバー オブジェクトに格納します。これは、クラス **Type** のメンバー関数へのポインターである必要があります。 そのメンバー関数 `operator()` は ( **left**.* `_Pm`)( ) を返すように定義されています。

## <a name="example"></a>例

`mem_fun_ref_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun_ref` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
