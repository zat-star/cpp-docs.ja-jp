---
title: "-Fe (EXE ファイルの名前) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /fe
dev_langs: C++
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b66c473c49527dff395d206594a314b527c4f914
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="fe-name-exe-file"></a>/Fe (EXE ファイルの名前の指定)
名前とディレクトリの .exe ファイルまたはコンパイラによって作成された DLL を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/Fepathname  
```  
  
## <a name="remarks"></a>コメント  
 このオプションを指定せず、コンパイラは、ファイルをコマンドラインおよび拡張子 .exe または .dll の指定された最初のソースまたはオブジェクトのファイルのベース名を使用して既定の名前には。  
  
 指定した場合、[(コンパイルなしのリンク)/c](../../build/reference/c-compile-without-linking.md)、リンクを行わずにコンパイルする**/Fe**も何も起こりません。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**全般**プロパティ ページ。  
  
4.  変更、**出力ファイル**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>」を参照してください。  
  
## <a name="example"></a>例  
 次のコマンドラインは、コンパイルし、現在のディレクトリ内のすべての C ソース ファイルをリンクします。 結果の実行可能ファイルは、PROCESS.exe をという名前し、C:\BIN のディレクトリに作成します。  
  
```  
CL /FeC:\BIN\PROCESS *.C  
```  
  
## <a name="example"></a>例  
 次のコマンドラインでの実行可能ファイルを作成する`C:\BIN`最初のソースまたはオブジェクトのファイルと同じベース名。  
  
```  
CL /FeC:\BIN\ *.C  
```  
  
## <a name="see-also"></a>関連項目  
 [出力ファイル (/F) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [パス名の指定](../../build/reference/specifying-the-pathname.md)