---
title: "-Fo (オブジェクト ファイルの名前) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
dev_langs:
- C++
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: be821daae88e7cc2149debb49889b79bc1a59699
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fo-object-file-name"></a>/Fo (オブジェクト ファイルの名前の指定)
既定値の代わりに使用する、オブジェクト (.obj) ファイルの名前またはディレクトリを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/Fopathname  
```  
  
## <a name="remarks"></a>コメント  
 このオプションを使用しない場合、オブジェクト ファイルは、ソース ファイルと .obj 拡張機能の基本名を使用します。 任意の名前と、拡張機能を使用することができますが、推奨される規則は、使用する obj.。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[出力ファイル]** プロパティ ページをクリックします。  
  
4.  変更、**オブジェクト ファイルの名前**プロパティです。  オブジェクト ファイルの開発環境での拡張機能を持つ必要があります obj.。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>」を参照してください。  
  
## <a name="example"></a>例  
 次のコマンド ライン THIS.obj をという名前の既存のディレクトリ、\OBJECT、ドライブ B にオブジェクト ファイルを作成します。  
  
```  
CL /FoB:\OBJECT\ THIS.C  
```  
  
## <a name="see-also"></a>参照  
 [出力ファイル (/F) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [パス名の指定](../../build/reference/specifying-the-pathname.md)