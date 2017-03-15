---
title: "/IGNOREIDL (属性を MIDL に挿入しない) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.IgnoreEmbeddedIDL"
  - "/ignoreidl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IGNOREIDL リンカー オプション"
  - "IGNOREIDL リンカー オプション"
  - "-IGNOREIDL リンカー オプション"
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /IGNOREIDL (属性を MIDL に挿入しない)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IGNOREIDL  
```  
  
## 解説  
 \/IGNOREIDL オプションは、ソース コード内の [IDL 属性](../../windows/idl-attributes.md)を .idl ファイル内に挿入しないことを指定します。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[埋め込み IDL\]プロパティ ページをクリックします。  
  
4.  \[埋め込み IDL の無視\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [\/IDLOUT \(MIDL 出力ファイルの指定\)](../Topic/-IDLOUT%20\(Name%20MIDL%20Output%20Files\).md)   
 [\/TLBOUT \(.TLB ファイル名の指定\)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [\/MIDL \(MIDL コマンド ライン オプションの指定\)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)