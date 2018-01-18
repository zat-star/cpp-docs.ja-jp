---
title: "-Fm (マップ ファイルの名前) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /fm
dev_langs: C++
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0a5111291ea92b8650896faf3117f0056510e5ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fm-name-mapfile"></a>/Fm (マップ ファイルの名前の指定)
対応する .exe ファイルまたは DLL 内に出現する順序でセグメントの一覧を含むマップ ファイルを生成するようにリンカーに指示します。  
  
## <a name="syntax"></a>構文  
  
```  
/Fmpathname  
```  
  
## <a name="remarks"></a>コメント  
 既定では、マップ ファイルは、対応する C または C++ ソース ファイルの基本名前が指定します。拡張機能をマップします。  
  
 指定する**/Fm**を指定した場合と同じ効果があります、 [/MAP (マップ ファイルの生成)](../../build/reference/map-generate-mapfile.md)リンカー オプション。  
  
 指定した場合[(コンパイルなしのリンク)/c](../../build/reference/c-compile-without-linking.md)をリンクすると、抑制する状況**/Fm**も何も起こりません。  
  
 マップ ファイル内のグローバル シンボルでは、コンパイラは、変数名に、先頭にアンダー スコアを追加するため、通常 1 つまたは複数先頭にアンダー スコアがあります。 マップ ファイルに表示されるグローバル シンボルの多くは、コンパイラと標準ライブラリによって内部的に使用されます。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [出力ファイル (/F) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [パス名の指定](../../build/reference/specifying-the-pathname.md)