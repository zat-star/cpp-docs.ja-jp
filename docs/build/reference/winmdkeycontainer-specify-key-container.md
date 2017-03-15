---
title: "/WINMDKEYCONTAINER (キー コンテナーの指定) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.WINMDKEYCONTAINER"
dev_langs: 
  - "C++"
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /WINMDKEYCONTAINER (キー コンテナーの指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

キー コンテナーを Windows メタデータ \(.winmd\) ファイルに署名する場合に指定します。  
  
```  
  
/WINMDKEYCONTAINER:name  
  
```  
  
## 解説  
 a \(.winmd\) ファイルに適用される [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md) リンカー オプションに似ています。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーを選択します。  
  
3.  **\[Windows メタデータ\]** プロパティ ページを選択します。  
  
4.  **\[Windows メタデータ キー コンテナー\]** ボックスで、場所を入力します。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)