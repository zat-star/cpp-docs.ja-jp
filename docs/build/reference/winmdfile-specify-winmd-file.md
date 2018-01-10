---
title: "WINMDFILE (winmd ファイルの指定) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
dev_langs: C++
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 153e5c0bd42b6fdba59e309483f25f09b86fe9fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE (winmd ファイルの指定)
によって生成される Windows ランタイム メタデータ (.winmd) 出力ファイルのファイル名を指定します、 [/WINMD](../../build/reference/winmd-generate-windows-metadata.md)リンカー オプション。  
  
```  
/WINMDFILE:filename  
```  
  
## <a name="remarks"></a>コメント  
 指定されている値を使用して`filename`を既定の .winmd ファイル名を上書きする (`binaryname`.winmd)。 ".Winmd"を追加しないことに注意してください。`filename`です。  複数の値が示されている場合、 **/WINMDFILE**コマンド ラインで、最後の 1 つが優先されます。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**リンカー**フォルダーです。  
  
3.  選択、 **Windows メタデータ**プロパティ ページ。  
  
4.  **Windows メタデータ ファイル**ボックスに、ファイルの場所を入力します。  
  
## <a name="see-also"></a>参照  
 [/WINMD (Windows メタデータの生成)](../../build/reference/winmd-generate-windows-metadata.md)   
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)