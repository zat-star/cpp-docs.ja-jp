---
title: "/WINMD (Windows メタデータの生成) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.GenerateWindowsMetadata"
dev_langs: 
  - "C++"
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /WINMD (Windows メタデータの生成)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows ランタイム メタデータ \(.winmd\) ファイルの生成を有効にします。  
  
```  
  
/WINMD[:{NO|ONLY}]  
```  
  
## 解説  
 \/WINMD  
 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリケーションの既定の設定です。  リンカーはバイナリ実行可能ファイルと .winmd メタデータ ファイルの両方を生成します。  
  
 \/WINMD:NO  
 リンカーは、実行可能ファイルが、.winmd ファイルを生成します。  
  
 \/WINMD:ONLY  
 リンカーは .winmd ファイルは、実行可能ファイルが生成されます。  
  
 既定でに、出力ファイル名 `binaryname`.winmd フォームがあります。  別のファイル名を指定するには、[\/WINMDFILE](../Topic/-WINMDFILE%20\(Specify%20winmd%20File\).md) オプションを使用します。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーを選択します。  
  
3.  **\[Windows メタデータ\]** プロパティ ページを選択します。  
  
4.  **\[Windows メタデータの生成\]** ドロップダウン リスト ボックスで、目的のオプションを選択します。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)