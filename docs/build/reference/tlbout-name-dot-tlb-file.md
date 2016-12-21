---
title: "/TLBOUT (.TLB ファイル名の指定) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.TypeLibraryFile"
  - "/tlbout"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".tlb ファイル, 名前を変更"
  - "/TLBOUT リンカー オプション"
  - "tlb ファイル, 名前を変更"
  - "TLBOUT リンカー オプション"
  - "-TLBOUT リンカー オプション"
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /TLBOUT (.TLB ファイル名の指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TLBOUT:[path\]filename  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *path*  
 絶対パスまたは相対パスを指定して、.tlb ファイルを作成する場所を指定します。  
  
 *filename*  
 MIDL コンパイラによって作成される .tlb ファイルの名前を指定します。  ファイル名の拡張子は付加されません。拡張子 .tlb が必要なときは、*filename*.tlb と指定します。  
  
## 解説  
 \/TLBOUT オプションは、.tlb ファイルの名前と拡張子を指定します。  
  
 [module](../../windows/module-cpp.md) 属性を持つプロジェクトをリンクするときは、Visual C\+\+ リンカーにより MIDL コンパイラが呼び出されます。  
  
 \/TLBOUT を指定しなかった場合、.tlb ファイルの名前は [\/IDLOUT](../Topic/-IDLOUT%20\(Name%20MIDL%20Output%20Files\).md) *filename* から取得されます。  \/IDLOUT も指定しなかった場合、.tlb ファイルの名前は vc70.tlb になります。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[埋め込み IDL\]プロパティ ページをクリックします。  
  
4.  \[タイプ ライブラリ\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [\/IGNOREIDL \(属性を MIDL に挿入しない\)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [\/MIDL \(MIDL コマンド ライン オプションの指定\)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)