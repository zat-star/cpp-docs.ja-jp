---
title: "-EP (#line ディレクティブしない stdout へのプリプロセス) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ep
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines
dev_langs: C++
helpviewer_keywords:
- copy preprocessor output to stdout
- preprocessor output, copy to stdout
- -EP compiler option [C++]
- EP compiler option [C++]
- /EP compiler option [C++]
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f57a4fb9fb35c60f051642120e2fc62d2306da7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ep-preprocess-to-stdout-without-line-directives"></a>/EP (#line ディレクティブを挿入しない stdout へのプリプロセス)
C および C++ ソース ファイルを前処理され、前処理済みファイルを標準出力デバイスにコピーされます。  
  
## <a name="syntax"></a>構文  
  
```  
/EP  
```  
  
## <a name="remarks"></a>コメント  
 プロセスでは、すべてのプリプロセッサ ディレクティブが実行されます。、マクロの展開が実行されて、およびコメントが削除されます。 プリプロセス済みの出力内のコメントを保持するために使用して、 [(保持コメント中に前処理)/C](../../build/reference/c-preserve-comments-during-preprocessing.md)オプションは**/EP**です。  
  
 **/EP**オプションには、コンパイルが行われません。 コンパイルのプリプロセス済みのファイルを再送信する必要があります。 **/EP**も抑制の出力ファイル、 **/FA**、 **/Fa**、および**/Fm**オプション。 詳細については、次を参照してください。 [/FA、/Fa (ファイルを一覧表示する)](../../build/reference/fa-fa-listing-file.md)と[/Fm (マップ ファイルの名前)](../../build/reference/fm-name-mapfile.md)です。  
  
 処理の後のステージ中に生成されたエラーは、元のソース ファイルではなく、前処理済みファイルの行番号を参照してください。 行番号を元のソース ファイルを参照する場合は、使用[/E (プリプロセス stdout へ)](../../build/reference/e-preprocess-to-stdout.md)代わりにします。 **/E**オプションは、追加`#line`をこの目的のための出力ディレクティブです。  
  
 と共にプリプロセス済みの出力を送信する`#line`ディレクティブは、ファイルを使用して、 [/P (プリプロセス出力ファイルへの)](../../build/reference/p-preprocess-to-a-file.md)オプションを代わりにします。  
  
 Stdout に前処理済みの出力を送信する`#line`、ディレクティブを使用して**/P**と**/EP**一緒にします。  
  
 プリコンパイル済みヘッダーを使用することはできません、 **/EP**オプション。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**プリプロセッサ**プロパティ ページ。  
  
4.  変更、**プリプロセス ファイルの生成**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>」を参照してください。  
  
## <a name="example"></a>例  
 次のコマンドラインは、ファイルをプリプロセス`ADD.C`コメントを保持、および標準出力デバイスに結果を表示します。  
  
```  
CL /EP /C ADD.C  
```  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)