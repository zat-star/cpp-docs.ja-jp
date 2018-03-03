---
title: "/Zc:externConstexpr (外部 constexpr 変数は有効にする) |Microsoft ドキュメント"
ms.custom: 
ms.date: 9/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Zc:externConstexpr
dev_langs:
- C++
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84037e5e8a942d51175d97957d0c05bd6f4aa29d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>/Zc:externConstexpr (外部 constexpr 変数は有効にする)

**/Zc:externConstexpr**コンパイラ オプションは C++ 標準に準拠しているし、の外部リンケージを許可するようにコンパイラに指示`constexpr`変数。 Visual Studio では、既定値は常に、`constexpr`変数内部リンケージを指定する場合でも、`extern`キーワード。

## <a name="syntax"></a>構文

> /Zc:externConstexpr [-]

## <a name="remarks"></a>コメント

**/Zc:externConstexpr**コンパイラ オプションは、コンパイラを使用して宣言された変数に外部リンケージを適用する`extern constexpr`です。 **/Zc:externConstexpr**オプションは、Visual Studio 2017 更新 15.5 以降を使用します。 以前のバージョンの Visual Studio で、既定で場合**/Zc:externConstexpr-**を指定すると、Visual Studio に内部リンケージを適用する`constexpr`変数場合であっても、`extern`キーワードを使用します。

ヘッダー ファイルには、宣言された変数が含まれている場合`extern constexpr`、マークする必要があります[__declspec(selectany)](../../cpp/selectany.md)リンクされているバイナリに 1 つのインスタンスに重複する宣言をマージするためにします。 それ以外の場合、リンカー エラー単一定義規則の違反をたとえば、LNK2005 を参照してください可能性があります。

### <a name="to-set-this-compiler-option-in-visual-studio"></a>このコンパイラ オプションを Visual Studio で使用するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. **構成プロパティ**、展開**C/C++**を選択し**コマンドライン**です。

1. 追加**/Zc:externConstexpr**または**/Zc:externConstexpr-**を**追加オプション:**ウィンドウです。

## <a name="see-also"></a>参照

[/Zc (準拠)](../../build/reference/zc-conformance.md)  
[auto キーワード](../../cpp/auto-keyword.md)