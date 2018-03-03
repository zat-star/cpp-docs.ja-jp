---
title: "-P (ファイルへのプリプロセス) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFile
- /p
- VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile
dev_langs:
- C++
helpviewer_keywords:
- /P compiler option [C++]
- -P compiler option [C++]
- P compiler option [C++]
- output files, preprocessor
- preprocessing output files
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f4de2f19820a846197806e0a24ddc213dd636c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="p-preprocess-to-a-file"></a>/P (プリプロセス出力のファイルへの書き込み)
C および C++ ソース ファイルを前処理し、ファイルをプリプロセス済みの出力を書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
/P  
```  
  
## <a name="remarks"></a>コメント  
 ファイルは、ソース ファイルと .i 拡張機能として同じ基本名にします。 プロセスでは、すべてのプリプロセッサ ディレクティブが実行されます。、マクロの展開が実行されて、およびコメントが削除されます。 プリプロセス済みの出力内のコメントを保持するために使用して、 [(保持コメント中に前処理)/C](../../build/reference/c-preserve-comments-during-preprocessing.md)オプションと共に**/P**です。  
  
 **/P**追加`#line`ディレクティブを先頭と末尾各インクルード ファイルの条件付きコンパイル用のプリプロセッサ ディレクティブによって削除された行に出力します。 これらのディレクティブは、前処理済みファイルの行を再設定します。 その結果、処理の後のステージ中に生成されたエラーは、前処理済みファイル内の行ではなく、元のソース ファイルの行番号を参照してください。 生成を抑制する`#line`、ディレクティブを使用して[/EP (#line ディレクティブしない stdout へのプリプロセス)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)だけでなく**/P**です。  
  
 **/P**オプションには、コンパイルが行われません。 使用する場合でも、.obj ファイルが生成されません[/Fo (オブジェクト ファイル名)](../../build/reference/fo-object-file-name.md)です。 コンパイルのプリプロセス済みのファイルを再送信する必要があります。 **/P**も抑制の出力ファイル、 **/FA**、 **/Fa**、および**/Fm**オプション。 詳細については、次を参照してください。 [/FA、/Fa (ファイルを一覧表示する)](../../build/reference/fa-fa-listing-file.md)と[/Fm (マップ ファイルの名前)](../../build/reference/fm-name-mapfile.md)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**プリプロセッサ**プロパティ ページ。  
  
4.  変更、**プリプロセス ファイルの生成**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>」を参照してください。  
  
## <a name="example"></a>例  
 次のコマンドラインを前処理`ADD.C`、コメントを保持、追加`#line`ディレクティブは、その結果をファイルに書き込みます`ADD.I`:  
  
```  
CL /P /C ADD.C  
```  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [/Fi (出力ファイル名のプリプロセス)](../../build/reference/fi-preprocess-output-file-name.md)