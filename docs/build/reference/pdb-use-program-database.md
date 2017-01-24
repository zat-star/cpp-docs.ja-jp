---
title: "/PDB (プログラム データベースの使用) | Microsoft Docs"
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
  - "/pdb"
  - "VC.Project.VCLinkerTool.ProgramDatabaseFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb ファイル, 作成"
  - "/PDB リンカー オプション"
  - "PDB ファイル, 作成"
  - "PDB リンカー オプション"
  - "-PDB リンカー オプション"
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /PDB (プログラム データベースの使用)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDB:filename  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *filename*  
 リンカーによって作成されるプログラム データベース \(PDB\) に対してユーザーが指定する名前。  既定の名前を置き換えます。  
  
## 解説  
 既定では、[\/DEBUG \(デバッグ情報の生成\)](../../build/reference/debug-generate-debug-info.md) を指定すると、デバッグ情報を取り込んだプログラム データベース \(PDB\) が作成されます。  .PDB の既定のファイル名は、プログラムのベース名に拡張子 .pdb を付けたものです。  
  
 \/PDB:*filename* を使用して、PDB ファイルの名前を指定します。  \/DEBUG を指定しなかった場合、\/PDB オプションは無視されます。  
  
 PDB ファイルは、最大 2 GB です。  
  
 詳細については、「[リンカー入力としての .pdb ファイル](../../build/reference/dot-pdb-files-as-linker-input.md)」を参照してください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[デバッグ\] プロパティ ページをクリックします。  
  
4.  \[プログラム データベース ファイルの生成\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)