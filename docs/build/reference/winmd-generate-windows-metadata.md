---
title: "-WINMD (Windows メタデータの生成) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs:
- C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7517ec459677659067e80930ee48caccf84d52f3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (Windows メタデータの生成)
Windows ランタイム メタデータ (.winmd) ファイルの生成を有効にします。  
  
```  
/WINMD[:{NO|ONLY}]  
```  
  
## <a name="remarks"></a>コメント  
 /WINMD  
 ユニバーサル Windows プラットフォーム アプリの既定の設定。 リンカーは、バイナリの実行可能ファイルとメタデータに .winmd ファイルの両方を生成します。  
  
 /WINMD:NO  
 バイナリ実行可能ファイルのみが .winmd ファイルではなく、リンカーが生成されます。  
  
 /WINMD:ONLY  
 .Winmd ファイルのみがバイナリ実行可能ファイルではなく、リンカーが生成されます。  
  
 既定では、出力ファイル名がフォーム`binaryname`.winmd です。 別のファイル名を指定するには、使用、 [/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md)オプション。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**リンカー**フォルダーです。  
  
3.  選択、 **Windows メタデータ**プロパティ ページ。  
  
4.  **Windows メタデータの生成**ドロップダウン リスト ボックスで、目的のオプションを選択します。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)