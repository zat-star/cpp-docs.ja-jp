---
title: "nothrow (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/03/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- nothrow_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5e0f5f40fbcfcb95952fd956060801e862e9cdaf
ms.sourcegitcommit: c2e990450ccd528d85b2783fbc63042612987cfd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2018
---
# <a name="nothrow-c"></a>nothrow (C++)

**Microsoft 固有の仕様**

関数の宣言に使用できる `__declspec` 拡張属性。

## <a name="syntax"></a>構文  
  
> *return-type* __declspec(nothrow) [*call-convention*] *function-name* ([*argument-list*])

## <a name="remarks"></a>コメント

すべての新しいコードを使用していることをお勧め、 [noexcept](noexcept-cpp.md)演算子なく`__declspec(nothrow)`です。

この属性は、宣言された関数、および、その呼び出す関数が例外をスローしないことをコンパイラに伝えます。 ただし、このディレクティブは適用されません。 つまり、これが、 [std::terminate](../standard-library/exception-functions.md#terminate)呼び出されるとは異なり`noexcept`、または**std:c:operator++ 17**モード (Visual Studio 2017 15.5 およびそれ以降のバージョン)、`throw()`です。

同期例外処理モデル (現在は既定のモデル) の場合、コンパイラはこのような関数で特定のアンワインド可能オブジェクトの有効期間を追跡する機構を削除して、コード サイズを大幅に小さくできます。 次のプリプロセッサ ディレクティブを指定するには、次の 3 つの関数の宣言と等価である**/std:c + + 14**モード。

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

**/Std:c + + 17**モード、`throw()`は、他のユーザーに使用する`__declspec(nothrow)`原因になるので`std::terminate`関数から例外がスローされた場合に呼び出されます。

`void __stdcall f3() throw();`宣言で、C++ 標準で定義されている構文を使用します。 C++ 17 で、`throw()`キーワードは推奨されなくなりました。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)  
[noexcept](noexcept-cpp.md)  
[キーワード](../cpp/keywords-cpp.md)  
