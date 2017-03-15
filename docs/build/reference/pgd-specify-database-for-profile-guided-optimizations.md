---
title: "/PGD (ガイド付き最適化のプロファイル用のデータベースの指定) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ProfileGuidedDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/PGD リンカー オプション"
  - "-PGD リンカー オプション"
ms.assetid: 9f312498-493b-461f-886f-92652257e443
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /PGD (ガイド付き最適化のプロファイル用のデータベースの指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/PGD:`filename`  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 `filename`  
 実行中のプログラムについての情報の保持に使用される .pgd ファイルの名前を指定します。  
  
## 解説  
 [\/LTCG:PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md) を使用する場合は、\/PGD を使用して、.pgd ファイルの既定以外の名前または場所を指定します。  \/PGD を指定しない場合、.pgd ファイルは、名前が出力ファイル \(.exe または .dll\) の名前と同じになり、そのリンクの呼び出し元と同じディレクトリに作成されます。  
  
 \/LTCG:PGOPTIMIZE を使用する場合は、\/PGD を使用して、最適化イメージの作成に使用する .pgd ファイルの名前を指定します。  
  
 詳細については、「[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)」を参照してください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[リンカー\]** ノードを展開します。  
  
4.  **\[最適化\]** プロパティ ページをクリックします。  
  
5.  **\[ガイド付きデータベースのプロファイル\]** プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)