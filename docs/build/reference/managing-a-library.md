---
title: "ライブラリの管理 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLibrarianTool.IgnoreAllDefaultLibraries"
  - "VC.Project.VCLibrarianTool.AdditionalDependencies"
  - "VC.Project.VCLibrarianTool.RemoveObjects"
  - "VC.Project.VCLibrarianTool.LibraryPaths"
  - "VC.Project.VCLibrarianTool.OutputFile"
  - "VC.Project.VCLibrarianTool.IgnoreDefaultLibraryNames"
  - "VC.Project.VCLibrarianTool.AdditionalLibraryDirectories"
  - "VC.Project.VCLibrarianTool.ListContentsFile"
  - "VC.Project.VCLibrarianTool.ListContents"
  - "VC.Project.VCLibrarianTool.SubSystemVersion"
  - "VC.Project.VCLibrarianTool.IgnoreDefaultLibraryName"
  - "VC.Project.VCLibrarianTool.SubSystem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CONVERT ライブラリ マネージャー オプション"
  - "/LIBPATH ライブラリ マネージャー オプション"
  - "/LINK50COMPAT ライブラリ マネージャー オプション"
  - "/LIST ライブラリ マネージャー オプション"
  - "/OUT ライブラリ マネージャー オプション"
  - "/REMOVE ライブラリ マネージャー オプション"
  - "/SUBSYSTEM ライブラリ マネージャー オプション"
  - "CONVERT ライブラリ マネージャー オプション"
  - "-CONVERT ライブラリ マネージャー オプション"
  - "LIB [C++], 管理 (COFF ライブラリを)"
  - "LIBPATH ライブラリ マネージャー オプション"
  - "-LIBPATH ライブラリ マネージャー オプション"
  - "LINK50COMPAT ライブラリ マネージャー オプション"
  - "-LINK50COMPAT ライブラリ マネージャー オプション"
  - "LIST ライブラリ マネージャー オプション"
  - "-LIST ライブラリ マネージャー オプション"
  - "オブジェクト ファイル"
  - "オブジェクト ファイル, ビルドと変更"
  - "OUT ライブラリ マネージャー オプション"
  - "-OUT ライブラリ マネージャー オプション"
  - "REMOVE ライブラリ マネージャー オプション"
  - "-REMOVE ライブラリ マネージャー オプション"
  - "SUBSYSTEM ライブラリ マネージャー オプション"
  - "-SUBSYSTEM ライブラリ マネージャー オプション"
ms.assetid: f56a8b85-fbdc-4c09-8d8e-00f0ffe1da53
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# ライブラリの管理
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LIB の既定のモードでは、COFF オブジェクトのライブラリをビルドしたり変更したりします。  \/EXTRACT \(オブジェクトのファイルへのコピー\) も \/DEF \(インポート ライブラリのビルド\) も指定されていないと、このモードになります。  
  
 オブジェクトとライブラリからライブラリをビルドするには、次の構文を使用します。  
  
```  
LIB [options...] files...  
```  
  
 このコマンドでは、1 つ以上の入力ファイルからライブラリを 1 つ作成します。  *files* では、COFF オブジェクト ファイル、32 ビット OMF オブジェクト ファイル、または既存の COFF ライブラリを指定します。  指定したファイルにあるすべてのオブジェクトが含まれたライブラリが作成されます。  入力ファイルとして 32 ビット OMF オブジェクト ファイルを指定すると、COFF フォーマットに変換された後でライブラリがビルドされます。  16 ビット版の LIB で作成されたライブラリに含まれている 32 ビット OMF オブジェクトは、使用できません。  あらかじめ 16 ビットの LIB を使ってオブジェクトを抽出し、その抽出したオブジェクト ファイルを 32 ビット LIB の入力ファイルとして使用してください。  
  
 既定では、最初のオブジェクト ファイルまたはライブラリ ファイルの基本名に拡張子 .lib を付けたものが、出力ファイル名になります。  出力ファイルは現在のフォルダーに作成されます。  同じ名前のファイルが既に存在する場合、そのファイルは出力ファイルで上書きされます。  既存のライブラリが上書きされないようにするには、\/OUT オプションで出力ファイル名を指定します。  
  
 以下は、ライブラリをビルドしたり変更したりするオプションです。  
  
 \/LIBPATH:`dir`  
 環境で指定されるライブラリのパスを一時的に変更します。  詳細については、LINK の [\/LIBPATH](../../build/reference/libpath-additional-libpath.md) オプションを参照してください。  
  
 \/LIST  
 出力ライブラリに関する情報を標準出力に表示します。  出力はファイルにリダイレクトできます。  \/LIST オプションを指定すると、既存のライブラリを変更せずに、その内容を確認できます。  
  
 \/NAME:*filename*  
 インポート ライブラリをビルドするときに、そのインポート ライブラリの対象となる DLL の名前を指定します。  
  
 \/NODEFAULTLIB  
 外部参照を解決するときに、検索するライブラリ リストから既定のライブラリを除外します。  詳細については、[\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) を参照してください。  
  
 \/OUT:*filename*  
 既定の出力ファイル名を変更します。  既定では、出力ライブラリは、コマンド ラインで指定した最初のライブラリまたはオブジェクト ファイルの基本名に拡張子 .lib が付いた名前で、現在のフォルダーに作成されます。  
  
 \/REMOVE:*object*  
 *object* で指定されたオブジェクトを出力ライブラリから削除します。  出力ライブラリの作成では、オブジェクト ファイルまたはライブラリの中にあるすべてのオブジェクトが連結された後、\/REMOVE で指定したオブジェクトが削除されます。  
  
 \/SUBSYSTEM:{CONSOLE &#124; EFI\_APPLICATION &#124; EFI\_BOOT\_SERVICE\_DRIVER &#124; EFI\_ROM &#124; EFI\_RUNTIME\_DRIVER &#124; NATIVE &#124; POSIX &#124; WINDOWS &#124; WINDOWSCE}\[,\#\[.\#\#\]\]  
 オペレーティング システムに対して、出力ライブラリにリンクして作成されたプログラムの実行方法を指示します。  詳細については、LINK の [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) オプションを参照してください。  
  
 コマンド ラインで指定する LIB オプションでは、大文字と小文字は区別されません。  
  
 LIB では、以下のライブラリ管理作業が可能です。  
  
-   ライブラリにオブジェクトを追加するには、既存のライブラリ ファイル名と、新しいオブジェクトの入っているファイル名を指定します。  
  
-   複数のライブラリを連結するには、該当するライブラリ ファイル名を指定します。  オブジェクトの追加とライブラリの連結は、1 つの LIB コマンドで実行できます。  
  
-   ライブラリ メンバーを新しいオブジェクトで置き換えるには、元のメンバー オブジェクトの入ったライブラリ名と、新しいオブジェクトのファイル名 \(または新しいオブジェクトの入ったライブラリ名\) を指定します。  複数の入力ファイルに同じ名前のオブジェクトがある場合は、最後に指定したオブジェクトが出力ライブラリに取り込まれます。  したがって、ライブラリ メンバーを置き換える場合は、古いオブジェクトの入ったライブラリを指定した後で、新しいオブジェクトまたはライブラリを指定します。  
  
-   ライブラリからメンバーを削除するには、\/REMOVE オプションを使用します。  \/REMOVE オプションがコマンド ラインのどこに指定されていても、入力オブジェクトがすべて連結されてから処理が行われます。  
  
> [!NOTE]
>  メンバーの削除とファイルへのメンバーの抽出は、同時には実行できません。  まず、\/EXTRACT でメンバー オブジェクトを抽出し、次に \/REMOVE オプションで再度 LIB を実行する必要があります。  これは、ほかの Microsoft 製品の 16 ビット LIB \(OMF ライブラリ用\) と異なる点です。  
  
## 参照  
 [LIB リファレンス](../../build/reference/lib-reference.md)