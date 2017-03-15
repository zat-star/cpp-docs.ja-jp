---
title: "/NODEFAULTLIB (ライブラリを無視する) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.IgnoreAllDefaultLibraries"
  - "VC.Project.VCLinkerTool.IgnoreDefaultLibraryNames"
  - "/nodefaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NODEFAULTLIB リンカー オプション"
  - "既定のライブラリ, 削除"
  - "無視 (ライブラリの) リンカー オプション"
  - "ライブラリ, 無視"
  - "NODEFAULTLIB リンカー オプション"
  - "-NODEFAULTLIB リンカー オプション"
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /NODEFAULTLIB (ライブラリを無視する)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NODEFAULTLIB[:library]   
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *library*  
 外部参照を解決するときに無視するライブラリを指定します。  
  
## 解説  
 \/NODEFAULTLIB オプションは、リンカーが外部参照を解決するときに検索するライブラリ リストから、検索の必要がない既定のライブラリを 1 つ以上除外します。  
  
 既定のライブラリへの参照を含まない .obj ファイルを作成するには、[\/Zl \(既定のライブラリ名の省略\)](../../build/reference/zl-omit-default-library-name.md) を使用します。  
  
 \/NODEFAULTLIB は、既定では、外部参照を解決するときに検索するライブラリ リストから、既定のライブラリをすべて除外します。  *library* パラメーター \(省略可能\) を指定して、外部参照を解決するときに検索するライブラリのリストから、複数のライブラリを指定して除外できます。  除外するライブラリごとに \/NODEFAULTLIB オプションを 1 つずつ指定します。  
  
 リンカーが外部参照を解決するときは、まず明示的に指定されたライブラリを検索し、次に \/DEFAULTLIB オプションで指定された既定のライブラリを検索します。その後、.obj ファイルで指定された既定のライブラリを検索します。  
  
 \/NODEFAULTLIB:*library* と [\/DEFAULTLIB:](../../build/reference/defaultlib-specify-default-library.md)*library* で同じライブラリ名を指定すると、前者の指定が優先されるためそのライブラリは検索されません。  
  
 たとえば、\/NODEFAULTLIB を使用して C ランタイム ライブラリなしでプログラムをビルドするときは、[\/ENTRY](../../build/reference/entry-entry-point-symbol.md) も使用して、プログラムのエントリ ポイント \(関数\) を指定することが必要な場合もあります。  詳細については、「[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)」を参照してください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーをクリックします。  
  
3.  **\[入力\]** プロパティ ページをクリックします。  
  
4.  **\[すべての既定のライブラリの無視\]** プロパティをクリックするか、無視するライブラリのリストを **\[特定のライブラリの無視\]** プロパティで指定します。  **\[コマンド ライン\]** プロパティ ページに、これらのプロパティに加えた変更内容が反映されます。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A>」および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)