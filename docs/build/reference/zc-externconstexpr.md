---
title: "/Zc:externConstexpr (外部 constexpr 変数は有効にする) |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/28/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zc:externConstexpr
dev_langs:
- C++
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6597bc96609ab051df56886ccc580516986f97ed
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>/Zc:externConstexpr (外部 constexpr 変数は有効にする)

**/Zc:externConstexpr**コンパイラ オプションは C++ 標準に準拠しているし、の外部リンケージを許可するようにコンパイラに指示`constexpr`変数。 Visual Studio では、既定値は常に、`constexpr`変数内部リンケージを指定する場合でも、`extern`キーワード。

## <a name="syntax"></a>構文

> **/Zc:externConstexpr**[**-**]

## <a name="remarks"></a>コメント

**/Zc:externConstexpr**コンパイラ オプションは、コンパイラを使用して宣言された変数に外部リンケージを適用する`extern constexpr`です。 以前のバージョンの Visual Studio で、既定で場合**/Zc:externConstexpr-**を指定すると、Visual Studio に内部リンケージを適用する`constexpr`変数場合であっても、`extern`キーワードを使用します。 **/Zc:externConstexpr**オプションは、Visual Studio 2017 更新 15.6 以降を使用します。 既定では無効になっているとします。 [寛容/-](permissive-standards-conformance.md)オプションが有効にしません**/Zc:externConstexpr**です。

ヘッダー ファイルには、宣言された変数が含まれている場合`extern constexpr`、マークする必要があります[__declspec(selectany)](../../cpp/selectany.md)リンクされているバイナリに 1 つのインスタンスに重複する宣言をマージするためにします。 それ以外の場合、リンカー エラー単一定義規則の違反をたとえば、LNK2005 を参照してください可能性があります。

### <a name="to-set-this-compiler-option-in-visual-studio"></a>このコンパイラ オプションを Visual Studio で使用するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 追加**/Zc:externConstexpr**または**/Zc:externConstexpr-**を**追加オプション:**ウィンドウです。

## <a name="see-also"></a>参照

[/Zc (準拠)](../../build/reference/zc-conformance.md)  
[auto キーワード](../../cpp/auto-keyword.md)