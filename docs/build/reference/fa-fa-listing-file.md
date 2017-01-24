---
title: "/FA、/Fa (リスティング ファイル) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.AssemblerListingLocation"
  - "VC.Project.VCCLCompilerTool.ConfigureASMListing"
  - "VC.Project.VCCLWCECompilerTool.AssemblerOutput"
  - "VC.Project.VCCLCompilerTool.AssemblerListingLocation"
  - "/fa"
  - "VC.Project.VCCLCompilerTool.AssemblerOutput"
  - "VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FA コンパイラ オプション [C++]"
  - "アセンブリのみのリスティング"
  - "FA コンパイラ オプション [C++]"
  - "-FA コンパイラ オプション [C++]"
  - "リスティング ファイルの種類"
ms.assetid: c7507d0e-c69d-44f9-b8e2-d2c398697402
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FA、/Fa (リスティング ファイル)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アセンブリ コードを含むリスティング ファイルを作成します。  
  
## 構文  
  
```  
/FA[c|s|u]  
/Fapathname  
```  
  
## 解説  
 引数を指定して、ソース コード、マシン語コード、リスティング ファイルの拡張子を制御します。  
  
 次の表は、**\/FA** に指定するさまざまな値についての説明です。  **\/FA** には複数の値を指定できます。  たとえば、**\/FAsu** と指定できます。  
  
|オプション|リスティング内容およびファイル名の拡張子|  
|-----------|--------------------------|  
|**\/FA**|アセンブリ コード、.asm|  
|**\/FAc**|マシン語コードとアセンブリ コード、.cod|  
|**\/FAs**|ソース コードとアセンブリ コード、.asm<br /><br /> **\/FAcs** が指定されている場合、ファイル名の拡張子は .cod になります。|  
|**\/FAu**|バイト順マーカー付きの出力ファイルが UTF\-8 形式で作成されます。  既定では、ファイル エンコーディングは ANSI ですが、リスティング ファイルがどのシステムでも正しく表示されるようにする場合、または Unicode ソース コード ファイルをコンパイラの入力として使用する場合は **\/FAu** を使用します。<br /><br /> **\/FAsu** を指定している場合、またはソース コード ファイルが UTF\-8 以外の Unicode エンコーディングを使用する場合は、.asm ファイルのコード行が正しく表示されないことがあります。|  
  
 既定では、リスティング ファイルはソース ファイルと同じ基本名を使用します。  **\/Fa** オプションを使用して、リスティング ファイルの名前とディレクトリを変更できます。  
  
|\/Fa の使用方法|結果|  
|----------------|--------|  
|**\/Fa**|1 *source\_file*.asm は各ソース・コード ファイルに作成されます。|  
|**\/Fa** *filename*|*filename*.asm は現在のディレクトリに配置されます。  1 つのソース コード ファイルをコンパイルする場合だけ有効です。|  
|**\/Fa** *filename.extension*|*filename.extension* は 現在のディレクトリに配置されます。  1 つのソース コード ファイルをコンパイルする場合だけ有効です。|  
|**\/Fa** *directory*\\|1 *source\_file*.asm は各ソース・コード ファイルの指定 *directory* に作成され、格納されます。  末尾に円記号 \(\\\) を付加する必要があります。  現在のディスクのパスだけを指定できます。|  
|**\/Fa** *directory*\\*filename*|*filename*.asm は指定 `directory`に配置されます。  1 つのソース コード ファイルをコンパイルする場合だけ有効です。|  
|**\/Fa** *directory*\\*filename.extension*|*filename.extension* は 指定 `directory`に配置されます。  1 つのソース コード ファイルをコンパイルする場合だけ有効です。|  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[出力ファイル\]** プロパティ ページをクリックします。  
  
4.  **\[ASM リストの場所\]** プロパティ \(**\/Fa** の場合\) または **\[アセンブリの出力\]** プロパティ \(**\/FA** の場合\) を変更します。**\/FAu** は、**\[追加のオプション\]** ボックスの **\[コマンド ライン\]** プロパティ ページで指定する必要があります。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   詳細については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerListingLocation%2A>」または「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerOutput%2A>」を参照してください。  **\/FAu** を指定するには、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## 使用例  
 次のコマンド ラインは、ソース コードとマシン語コードを含むリスティング ファイル HELLO.cod を作成します。  
  
```  
CL /FAcs HELLO.CPP  
```  
  
## 参照  
 [出力ファイル \(\/F\) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [パス名の指定](../Topic/Specifying%20the%20Pathname.md)