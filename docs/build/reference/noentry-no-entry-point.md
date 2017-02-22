---
title: "/NOENTRY (エントリ ポイントなし) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ResourceOnlyDLL"
  - "/noentry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NOENTRY リンカー オプション [C++]"
  - "DLL [C++], 作成"
  - "エントリ ポイント [C++], リンカー指定"
  - "NOENTRY リンカー オプション"
  - "-NOENTRY リンカー オプション"
  - "リソース専用 DLL [C++], 作成"
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /NOENTRY (エントリ ポイントなし)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NOENTRY  
```  
  
## 解説  
 \/NOENTRY オプションは、実行可能コードが含まれていない、リソースだけの DLL を作成するために必要です。  詳細については、「[リソースのみの DLL の作成](../../build/creating-a-resource-only-dll.md)」を参照してください。  
  
 このオプションを使用すると、`_main` 関数への参照が DLL ファイルにリンクされなくなります。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーを選択します。  
  
3.  **\[詳細\]** プロパティ ページをクリックします。  
  
4.  \[エントリ ポイントなし\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>」を参照してください。  
  
## 参照  
 [リソースのみの DLL の作成](../../build/creating-a-resource-only-dll.md)   
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)