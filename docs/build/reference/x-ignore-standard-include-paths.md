---
title: "-X (標準を無視するパスを含める) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /x
- VC.Project.VCCLCompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLWCECompilerTool.OVERWRITEStandardIncludePath
dev_langs: C++
helpviewer_keywords:
- /X compiler option [C++]
- include files, ignore standard path
- -X compiler option [C++]
- include directories, ignore standard
- X compiler option
- Ignore Standard Include Paths compiler option
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a15294e1a63b16124d8907639fbd2e6bb705f1aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="x-ignore-standard-include-paths"></a>/X (標準インクルード パスの無視)
コンパイラが PATH および INCLUDE 環境変数で指定したディレクトリ内のインクルード ファイルを検索するを防ぎます。  
  
## <a name="syntax"></a>構文  
  
```  
/X  
```  
  
## <a name="remarks"></a>コメント  
 このオプションを使用することができます、 [/I (追加インクルード ディレクトリ)](../../build/reference/i-additional-include-directories.md) (**/I**`directory`) オプション。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**プリプロセッサ**プロパティ ページ。  
  
4.  変更、**標準インクルード パスの無視**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>」を参照してください。  
  
## <a name="example"></a>例  
 次のコマンドで`/X`PATH および INCLUDE 環境変数で指定された位置を無視するようにコンパイラに指示し、`/I`を検索するディレクトリを指定ファイルを含めます。  
  
```  
CL /X /I \ALT\INCLUDE MAIN.C  
```  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)