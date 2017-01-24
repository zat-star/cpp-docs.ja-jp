---
title: "/WINMDKEYFILE (キー ファイルの指定) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.WINMDKeyFile"
dev_langs: 
  - "C++"
ms.assetid: 65d88fdc-fff9-49ea-8cfc-b2f408741734
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /WINMDKEYFILE (キー ファイルの指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

キーを指定するか、署名するキーのペアは、Windows ランタイム メタデータ \(.winmd\) ファイル。  
  
```  
  
/WINMDKEYFILE:filename  
  
```  
  
## 解説  
 .winmd ファイルに適用される [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) リンカー オプションに似ています。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーを選択します。  
  
3.  **\[Windows メタデータ\]** プロパティ ページを選択します。  
  
4.  **\[Windows メタデータ キー ファイル\]** ボックスに、ファイルの場所を入力します。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)