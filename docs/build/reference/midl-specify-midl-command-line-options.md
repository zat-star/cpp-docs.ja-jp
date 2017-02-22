---
title: "/MIDL (MIDL コマンド ライン オプションの指定) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/midl"
  - "VC.Project.VCLinkerTool.MidlCommandFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MIDL リンカー オプション"
  - "MIDL"
  - "MIDL リンカー オプション"
  - "-MIDL リンカー オプション"
  - "MIDL, コマンド ライン オプション"
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /MIDL (MIDL コマンド ライン オプションの指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MIDL:@file  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 `file`  
 [MIDL コマンド ライン オプション](http://msdn.microsoft.com/library/windows/desktop/aa366839)が記述されているファイルの名前。  
  
## 解説  
 IDL ファイルから TLB ファイルへのすべての変換オプションは、`file` 内で指定する必要があります。MIDL コマンド ライン オプションは、リンカーのコマンド ラインでは指定できません。  \/MIDL を指定しないと、オプションの指定がない IDL ファイル名だけで MIDL コンパイラが起動されます。  
  
 ファイルには、1 行に 1 つずつ MIDL コマンド ライン オプションを指定します。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[埋め込み IDL\]プロパティ ページをクリックします。  
  
4.  \[MIDL コマンド\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [\/IDLOUT \(MIDL 出力ファイルの指定\)](../Topic/-IDLOUT%20\(Name%20MIDL%20Output%20Files\).md)   
 [\/IGNOREIDL \(属性を MIDL に挿入しない\)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [\/TLBOUT \(.TLB ファイル名の指定\)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)