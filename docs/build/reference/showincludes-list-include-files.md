---
title: "-showincludes (一覧は、ファイルを含める) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
dev_langs: C++
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cb88ff6d8a314ebd5cb0390f2c920f5b1d04e3e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="showincludes-list-include-files"></a>/showIncludes (インクルード ファイル一覧)
コンパイラでインクルード ファイルの一覧を出力します。 入れ子になった含めるファイルも表示されている (含まれているファイルからファイルをインクルードする)。  
  
## <a name="syntax"></a>構文  
  
```  
/showIncludes  
```  
  
## <a name="remarks"></a>コメント  
 コンパイル時に、インクルード ファイルを検出したときにメッセージは、出力がたとえばです。  
  
```  
Note: including file: d:\MyDir\include\stdio.h  
```  
  
 入れ子になった含めるなどのファイルは、インデントは、入れ子のレベルごとに 1 つのスペースで示されます。  
  
```  
Note: including file: d:\temp\1.h  
Note: including file:  d:\temp\2.h  
```  
  
 この場合、`2.h`が内から含まれている`1.h`、したがってインデントします。  
  
 **/ShowIncludes**オプションを出力する`stderr`ではなく、`stdout`です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**詳細**プロパティ ページ。  
  
4.  変更、**インクルード ファイルの表示**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)