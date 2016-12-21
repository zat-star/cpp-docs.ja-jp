---
title: "/NXCOMPAT (データ実行防止との互換性) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/NXCOMPAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NXCOMPAT リンカー オプション"
  - "NXCOMPAT リンカー オプション"
  - "-NXCOMPAT リンカー オプション"
ms.assetid: 5858e7ff-24d3-4ac3-9046-af2c9e220d9b
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /NXCOMPAT (データ実行防止との互換性)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

実行可能ファイルで Windows データ実行防止機能との互換性がテストされたことを示します。  
  
## 構文  
  
```  
/NXCOMPAT[:NO]  
```  
  
## 解説  
 **\/NXCOMPAT** は既定でオンになります。  
  
 **\/NXCOMPAT:NO** を使用すると、実行可能ファイルがデータ実行防止と互換性がないことを明示的に指定できます。  
  
 データ実行防止の詳細については、以下を参照してください。  
  
-   [Windows XP Service Pack 2、Windows XP Tablet PC Edition 2005、および Windows Server 2003 のデータ実行防止 \(DEP\) 機能の詳細](http://go.microsoft.com/fwlink/?LinkID=157771) \(マイクロソフト サポート オンライン\)  
  
-   ["Data Execution Prevention \(データ実行防止\)"](http://go.microsoft.com/fwlink/?LinkID=157770) MSDN Web サイト  
  
-   ["Data Execution Prevention \(Windows Embedded\) \(データ実行防止 \(Windows Embedded\)\)"](http://go.microsoft.com/fwlink/?LinkID=157768) MSDN Web サイト  
  
### このリンカー オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにオプションを入力します。  
  
### このリンカーをコードから設定するには  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)