---
title: "/Zc:referenceBinding (参照のバインディング規則の実施) |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8e3b10f5b2108a4c0e29d802951015749775a27
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc:referenceBinding (参照のバインディング規則の適用)

ときに、 **/Zc:referenceBinding**オプションを指定すると、コンパイラでは、一時的にバインドする非定数の左辺値参照することはできません。

## <a name="syntax"></a>構文

> **/Zc:referenceBinding**[**-**]

## <a name="remarks"></a>コメント

場合**/Zc:referenceBinding**を指定すると、コンパイラが標準の c++ 11 の 8.5.3 に依存して、一時的なユーザー定義型を非定数の左辺値参照にバインドする式は許可されません。 既定では、または**/Zc:referenceBinding-**指定すると、コンパイラは、Microsoft 拡張機能としては、このような式を使用できますが、レベル 4 の警告を発行します。 使用することお勧めをコードのセキュリティ、移植性および適合性、 **/Zc:referenceBinding**です。

**/Zc:referenceBinding**オプションは既定でオフになっています。 [寛容/-](permissive-standards-conformance.md)コンパイラ オプションでは、このオプションは、暗黙的に設定しますを使用してオーバーライドできます**/Zc:referenceBinding-**です。

## <a name="example"></a>例

このサンプルでは、Microsoft 拡張機能により、ユーザー定義型の一時オブジェクトを非定数の左辺値参照にバインドすることを示します。

```cpp
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

void main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを**/Zc:referenceBinding**を選択し**OK**です。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (準拠)](../../build/reference/zc-conformance.md)<br/>
