---
title: "-Yl (デバッグ ライブラリの PCH 参照の挿入) |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /yl
dev_langs: C++
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6e777977f6d869d2bbc28d980f6445851e54396b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl (デバッグ ライブラリの PCH 参照の挿入)

**/Yl**オプションがプリコンパイル済みヘッダー ファイルの一般的な記号を作成し、プリコンパイル済みヘッダーを使用しているすべてのファイルでこのシンボルへの参照を挿入します。 これにより、プリコンパイル済みヘッダーを使用するすべてのファイルのデバッガーにプリコンパイル済みヘッダーのシンボルの完全な型情報が利用可能なにします。 既定では、このオプションは有効になっています。 このオプションを使用するには、プリコンパイル済みヘッダーを使用してリンク先のライブラリのデバッグ情報がないため、リンカー エラーを回避できます。

## <a name="syntax"></a>構文

>**/Yl**  
>**/Yl**_名_  
>**/Yl-**  

### <a name="arguments"></a>引数

*name*  
および保存で参照されているオブジェクト ファイルを定義またはプリコンパイル済みヘッダーを使用するシンボルを定義するために使用するオプションの名前。

*\-*  
ダッシュ (-) が明示的に無効になります、 **/Yl**コンパイラ オプション。

## <a name="remarks"></a>コメント

**/Yl**オプションにより、デバッガーは、プリコンパイル済みヘッダーを含むすべてのファイルでプリコンパイル済みヘッダーでの詳細については、型を取得します。 このオプションは、内部シンボル名を作成でプリコンパイル済みヘッダーを作成するために使用するオブジェクト ファイル内のシンボル定義を挿入、 [/Yc](../../build/reference/yc-create-precompiled-header-file.md)オプション、およびプリコンパイルされたを含むすべてのファイル内のシンボルへの参照を挿入ヘッダーを使用して、 [/Yu](../../build/reference/yu-use-precompiled-header-file.md)コンパイラ オプション。 プリコンパイル済みヘッダーを使用するすべてのソース ファイルは、名前付きのシンボルを参照して、ため、リンカーは常に、シンボルとデバッグ情報関連のプリコンパイル済みヘッダーを定義するオブジェクト ファイルをリンクします。 既定では、このオプションは有効になっています。

**/Yl**_名前_プリコンパイル済みヘッダー ファイルの識別のシンボルを明示的に作成するオプションを使用します。 コンパイラを使用して、*名前*シンボルを作成するのような引数\_ \_ @@ \_PchSym\_@00@... @*名*ここで、省略記号 (...) を表しますがリンカーによって生成された文字の文字列。 引数を省略すると、コンパイラはシンボル名を自動的に生成されます。

**/Yl-**既定の動作を無効にし、プリコンパイル済みヘッダーを含むオブジェクト ファイルに特定のシンボル参照を配置しません。 このオプションは、プリコンパイル済みヘッダー ファイルが存在せずにコンパイルされたファイルに必要なにあります。

使用する場合**/Yl-**、 **/Yc**と[/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)コンパイラ、ライブラリをビルドするオプションがプリコンパイル済みヘッダー ファイルに格納されているデバッグ情報を含むを作成します。オブジェクト ファイルではなく .pdb ファイル。 [LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md)エラーまたは[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)をこのライブラリを使用するビルドの警告が発生する可能性が、プリコンパイル済みヘッダーを作成するソース ファイルが使用されている場合は、プリコンパイル済みヘッダーはすべてのシンボルが定義されていません。 リンカーが関連付けられているプリコンパイル済みヘッダーのデバッグ情報と共に、リンクからのこのライブラリ オブジェクト ファイルを除外するには、オブジェクト ファイルでは nothing ライブラリ クライアントで参照されているときにします。 問題を解決するには、次のように指定します。 **/Yl**を使用すると**/Yc**プリコンパイル済みヘッダー ファイルを作成すると**/Yu**を使用します。 これにより、デバッグ情報を含むオブジェクト ファイルがビルドに含まれています。

プリコンパイル済みヘッダーの詳細についてを参照してください。

- [/Y (プリコンパイル済みヘッダー)](../../build/reference/y-precompiled-headers.md)

- [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**コマンドライン**プロパティ ページで、 **C/C++**フォルダーです。

1. 追加、 **/Yl**_名前_コンパイラ オプション、**追加オプション**ボックス。 選択**OK**して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)  
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)  
