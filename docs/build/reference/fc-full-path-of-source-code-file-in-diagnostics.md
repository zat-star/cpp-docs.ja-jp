---
title: FC (診断のソース コード ファイルの完全パス) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.UseFullPaths
- /FC
dev_langs:
- C++
helpviewer_keywords:
- /FC compiler option [C++]
- -FC compiler option [C++]
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3bddc92d8c013fd3b4e2425b7f85b084651cdafe
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="fc-full-path-of-source-code-file-in-diagnostics"></a>/FC (診断時のソース コード ファイルの完全パス)

コンパイラで診断に、コンパイラに渡されるソース コード ファイルの完全パスを表示します。

## <a name="syntax"></a>構文

> /FC

## <a name="remarks"></a>コメント

次のコード サンプルを検討してください。

```cpp
// compiler_option_FC.cpp
int main( ) {
   int i   // C2143
}
```

せず**/FC**、診断用のテキストはこの診断テキストのようになります。

- compiler_option_FC.cpp(5): エラー C2143: 構文エラー: 見つかりません ';' は、前に '}'

**/FC**、診断用のテキストはこの診断テキストのようになります。

- c:\test\compiler_option_fc.cpp(5): エラー C2143: 構文エラー: 見つかりません ';' は、前に '}'

 **/FC**を使用する場合は、ファイル名の完全なパスを表示する場合にも必要、 &#95;&#95;ファイル&#95;&#95;マクロです。 参照してください[定義済みマクロ](../../preprocessor/predefined-macros.md)について&#95;&#95;ファイル&#95;&#95;です。

**/FC**がオプションが含まれる**/ZI**です。 詳細については**/ZI**を参照してください[/Z7、/Zi、/ZI (デバッグ情報の形式)](../../build/reference/z7-zi-zi-debug-information-format.md)です。

**/FC**小文字で完全なパスを出力します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **詳細**プロパティ ページ。

1. 変更、**完全パスの使用**プロパティです。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)   
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
