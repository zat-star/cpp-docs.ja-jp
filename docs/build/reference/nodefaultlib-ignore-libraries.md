---
title: "-NODEFAULTLIB (ライブラリの無視) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLinkerTool.OVERWRITEDefaultLibraryNames
- /nodefaultlib
dev_langs: C++
helpviewer_keywords:
- default libraries, removing
- -NODEFAULTLIB linker option
- libraries, ignore
- NODEFAULTLIB linker option
- /NODEFAULTLIB linker option
- ignore libraries linker option
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 24045fbbba41eb9d7ca1929a86d3dd599d3490ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nodefaultlib-ignore-libraries"></a>/NODEFAULTLIB (ライブラリを無視する)
```  
/NODEFAULTLIB[:library]   
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *ライブラリ*  
 外部参照を解決するときに無視するライブラリです。  
  
## <a name="remarks"></a>コメント  
 /NODEFAULTLIB オプションを使用すると、リンカーは、外部参照を解決するときに、検索するライブラリの一覧から 1 つまたは複数の既定のライブラリを削除します。  
  
 既定のライブラリへの参照が含まれていない .obj ファイルを作成するには、使用[/Zl (既定ライブラリ名の省略)](../../build/reference/zl-omit-default-library-name.md)です。  
  
 既定では、/NODEFAULTLIB は、外部参照を解決するときに、検索するライブラリの一覧からすべての既定のライブラリを削除します。 省略可能な*ライブラリ*パラメーターでは、外部参照を解決するときに、検索するライブラリの一覧から、指定されたライブラリまたはライブラリを削除することができます。 除外する各ライブラリの 1 つの/NODEFAULTLIB オプションを指定します。  
  
 リンカーは、明示的に指定し、次にライブラリが/DEFAULTLIB オプションで指定された既定のライブラリに、次の .obj ファイルの既定のライブラリを最初に検索して、外部定義への参照を解決します。  
  
 /NODEFAULTLIB:*ライブラリ*オーバーライド[/DEFAULTLIB:](../../build/reference/defaultlib-specify-default-library.md)*ライブラリ*とき同じ*ライブラリ*両方の名前を指定します。  
  
 /NODEFAULTLIB を使用する場合など、C ランタイム ライブラリなしプログラムをビルドするしなければならない場合も使用[/ENTRY](../../build/reference/entry-entry-point-symbol.md)をプログラムでエントリ ポイント (関数) を指定します。 詳しくは、「[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)」をご覧ください。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**入力**プロパティ ページ。  
  
4.  選択、**すべて既定のライブラリの無視**プロパティで無視するライブラリの一覧を指定または、**特定のライブラリの無視**プロパティです。 **コマンドライン**プロパティ ページには、これらのプロパティに加えた変更の効果が表示されます。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A>」および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)