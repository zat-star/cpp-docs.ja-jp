---
title: "-WINMD (Windows メタデータの生成) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs: C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 903ab6875457aa8c069c47a2be7f8ff1f5c884a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (Windows メタデータの生成)
Windows ランタイム メタデータ (.winmd) ファイルの生成を有効にします。  
  
```  
/WINMD[:{NO|ONLY}]  
```  
  
## <a name="remarks"></a>コメント  
 /WINMD  
 既定の設定[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]アプリ。 リンカーは、バイナリの実行可能ファイルとメタデータに .winmd ファイルの両方を生成します。  
  
 /WINMD:NO  
 バイナリ実行可能ファイルのみが .winmd ファイルではなく、リンカーが生成されます。  
  
 /WINMD: のみ  
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