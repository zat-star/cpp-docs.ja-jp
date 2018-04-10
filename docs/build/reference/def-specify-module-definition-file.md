---
title: -DEF (モジュール定義ファイルの指定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ModuleDefinitionFile
- /def
dev_langs:
- C++
helpviewer_keywords:
- module definition files, specifying
- DEF linker option
- -DEF linker option
- module definition files
- /DEF linker option
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c35e2c834edd4215c6b2bd671e4fc2ba79262aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="def-specify-module-definition-file"></a>/DEF (モジュール定義ファイルの指定)
```  
/DEF:filename  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *ファイル名*  
 モジュール定義ファイルをリンカーに渡される (.def) の名前。  
  
## <a name="remarks"></a>コメント  
 /DEF オプションは、モジュール定義ファイル (.def) をリンカーに渡します。 1 つだけの .def ファイルは、リンクを指定できます。 .Def ファイルに関する詳細については、「[モジュール定義ファイル](../../build/reference/module-definition-dot-def-files.md)です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**入力**プロパティ ページ。  
  
4.  変更、**モジュール定義ファイル**プロパティです。  
  
 開発環境での .def ファイルを指定するにをその他のファイルと共にプロジェクトに追加し、/DEF オプションにファイルを指定します。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)