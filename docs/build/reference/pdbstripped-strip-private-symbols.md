---
title: "/PDBSTRIPPED (プライベート シンボルの除去) | Microsoft Docs"
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
  - "/pdbstripped"
  - "VC.Project.VCLinkerTool.StripPrivateSymbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb ファイル, 除去 (プライベート シンボルの)"
  - "/PDBSTRIPPED リンカー オプション"
  - "PDB ファイル, 除去 (プライベート シンボルの)"
  - "PDBSTRIPPED リンカー オプション"
  - "-PDBSTRIPPED リンカー オプション"
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /PDBSTRIPPED (プライベート シンボルの除去)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDBSTRIPPED:pdb_file_name  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *pdb\_file\_name*  
 リンカーによって作成されたストライプ化プログラム データベース \(PDB\) に対してユーザーが指定する名前。  
  
## 解説  
 PDB ファイルを生成するいずれかのコンパイラ オプションまたはリンカー オプション \([\/DEBUG](../../build/reference/debug-generate-debug-info.md)、[\/Z7](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)、\/Zd、または \/Zi\) を使ってプログラム イメージをビルドするときに \/PDBSTRIPPED オプションを指定すると、2 番目のプログラム データベース \(PDB\) ファイルが作成されます。  2 番目の PDB ファイルでは、顧客に提供しないシンボルが省かれています。  2 番目の PDB ファイルの内容は、次のとおりです。  
  
-   パブリック シンボル。  
  
-   オブジェクト ファイルの一覧とそれらが関係する実行可能ファイル部分。  
  
-   スタック内を移動するためのフレーム ポインター最適化 \(FPO: Frame Pointer Optimization\) のデバッグ レコード。  
  
 シンボルなどが除去された PDB ファイルには、以下のものは含まれません。  
  
-   型情報。  
  
-   行番号情報。  
  
-   関数、ローカル データ、静的データなどのオブジェクト ファイル単位の CodeView シンボル。  
  
 \/PDBSTRIPPED の指定時には、完全な PDB ファイルも生成されます。  
  
 PDB ファイルを作成しない場合、\/PDBSTRIPPED は無視されます。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[デバッグ\] プロパティ ページをクリックします。  
  
4.  \[プライベート シンボルの削除\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)