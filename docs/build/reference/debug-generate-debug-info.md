---
title: "/DEBUG (デバッグ情報の生成) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.GenerateDebugInformation"
  - "/debug"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb ファイル, 生成 (デバッグ情報の)"
  - "/DEBUG リンカー オプション"
  - "DEBUG リンカー オプション"
  - "-DEBUG リンカー オプション"
  - "デバッグ [C++], デバッグ情報ファイル"
  - "デバッグ [C++], リンカー オプション"
  - "生成 (デバッグ情報の) リンカー オプション"
  - "PDB ファイル"
  - "pdb ファイル, 生成 (デバッグ情報の)"
  - "プログラム データベース [C++]"
ms.assetid: 1af389ae-3f8b-4d76-a087-1cdf861e9103
caps.latest.revision: 11
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DEBUG (デバッグ情報の生成)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DEBUG  
```  
  
## 解説  
 \/DEBUG オプションは、.exe ファイルまたは DLL のデバッグ情報を作成します。  
  
 デバッグ情報は、プログラム データベース \(PDB ファイル\) に書き込まれます。  この PDB ファイルは、以降のビルドで更新されます。  
  
 デバッグ用に生成された .exe ファイルや DLL ファイルには、対応する PDB ファイルの名前とパスが記述されています。  デバッガーでプログラムをデバッグするときにこの名前が読み取られ、その PDB ファイルが使われます。  プログラム データベースの名前として、プログラムのベース名と拡張子 .pdb が使用され、PDB ファイルを作成したパスも .exe ファイルと DLL ファイルに書き込まれます。  既定の名前をオーバーライドするには、[\/PDB](../../build/reference/pdb-use-program-database.md) を設定し、別のファイル名を指定します。  
  
 [\/Zd \(行番号のみ\)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) または [\/Z7 \(C7 互換\)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) オプションを指定すると、.obj ファイルにデバッグ情報が保存されます。  [\/Zi \(プログラム データベースを使用\)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) コンパイラ オプションを指定すると、.obj ファイルのデバッグ情報が PDB ファイルに保存されます。  リンカーはオプジェクトの PDB ファイルを探すときに、まず .obj ファイルに書き込まれた絶対パスを検索し、そこで見つからない場合は .obj ファイルの置かれているディレクトリを検索します。  オブジェクトの PDB ファイルの名前やディレクトリをリンカーに指定することはできません。  
  
 \/DEBUG を指定すると [\/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) も指定されます。  
  
 \/DEBUG は [\/OPT](../../build/reference/opt-optimizations.md) オプションの既定値を REF から NOREF、および ICF から NOICF に変更します。このため、\/OPT:REF または \/OPT:ICF を明示的に指定する必要があります。  
  
 .PDB ファイルと .DBG ファイルの詳細については、サポート技術情報の「INFO: PDB and DBG Files \- What They Are and How They Work \(Q121366\)」を参照してください。  MSDN ライブラリのサポート技術情報の文書"、または"を参照してください。[http:\/\/support.microsoft.com](http://support.microsoft.com/)  
  
 デバッグ情報を格納する .exe や .dll を作成することはできません。  デバッグ情報は常に .pdb ファイルに格納されます。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  **デバッグ** プロパティ ページをクリックします。  
  
4.  \[デバッグ情報の生成\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)