---
title: "/MD、/MT、/LD (ランタイム ライブラリの使用) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/ld"
  - "/mt"
  - "VC.Project.VCCLWCECompilerTool.RuntimeLibrary"
  - "VC.Project.VCCLCompilerTool.RuntimeLibrary"
  - "/md"
  - "/ml"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LD コンパイラ オプション [C++]"
  - "/MD コンパイラ オプション [C++]"
  - "/MDd コンパイラ オプション [C++]"
  - "/MT コンパイラ オプション [C++]"
  - "/MTd コンパイラ オプション [C++]"
  - "_STATIC_CPPLIB シンボル"
  - "DLL [C++], コンパイラ オプション"
  - "LD コンパイラ オプション [C++]"
  - "-LD コンパイラ オプション [C++]"
  - "LIBC.lib"
  - "LIBCD.lib"
  - "LIBCMT.lib"
  - "LIBCMTD.lib"
  - "MD コンパイラ オプション [C++]"
  - "-MD コンパイラ オプション [C++]"
  - "MDd コンパイラ オプション [C++]"
  - "-MDd コンパイラ オプション [C++]"
  - "MSVCRT.lib"
  - "MSVCRTD.lib"
  - "MT コンパイラ オプション [C++]"
  - "-MT コンパイラ オプション [C++]"
  - "MTd コンパイラ オプション [C++]"
  - "-MTd コンパイラ オプション [C++]"
  - "multithread コンパイラ オプション"
  - "スレッド処理 [C++], multithread コンパイラ オプション"
ms.assetid: cf7ed652-dc3a-49b3-aab9-ad60e5395579
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# /MD、/MT、/LD (ランタイム ライブラリの使用)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マルチスレッド モジュールが DLL であるかどうかを指定し、ランタイム ライブラリのリテール バージョンまたはデバッグ バージョンを指定します。  
  
## 構文  
  
```  
/MD[d]  
/MT[d]  
/LD[d]  
```  
  
## 解説  
  
|オプション|説明|  
|-----------|--------|  
|**\/MD**|アプリケーションでランタイム ライブラリのマルチスレッド対応および DLL 対応バージョンが使用されます。  `_MT` および `_DLL` を定義し、コンパイラにライブラリ名 MSVCRT.lib を .obj ファイルに挿入させます。<br /><br /> このオプションを使用してコンパイルされたアプリケーションは、MSVCRT.lib に静的にリンクされます。  このライブラリには、リンカーが外部参照を解決できるようにするコード レイヤーが用意されています。  実際に動くコードは MSVCR*versionnumber*.DLL に入っているため、実行時には、MSVCRT.lib とリンクしているアプリケーションがこの DLL を使用できるようにしておく必要があります。|  
|**\/MDd**|`_DEBUG`、`_MT`、および `_DLL` を定義します。アプリケーションで、マルチスレッド対応バージョンおよび DLL 対応バージョンのランタイム ライブラリが使用されます。  また、コンパイラによって、ライブラリ名 MSVCRTD.lib が .obj ファイルに挿入されます。|  
|**\/MT**|アプリケーションで、マルチスレッド バージョンの静的なランタイム ライブラリが使用されます。  `_MT` を定義します。また、コンパイラにライブラリ名 LIBCMT.lib を .obj ファイルに挿入させるため、リンカーは LIBCMT.lib を使って外部シンボルを解決します。|  
|**\/MTd**|`_DEBUG` および `_MT` を定義します。  このオプションによって、リンカーが LIBCMTD.lib を使用して外部シンボルを解決できるように、コンパイラによりライブラリ名 LIBCMTD.lib が .obj ファイルに挿入されます。|  
|**\/LD**|DLL を作成します。<br /><br /> **\/DLL** オプションをリンカーに渡します。  リンカーは `DllMain` 関数の有無を確認します。  `DllMain` 関数が記述されていないと、TRUE を返す `DllMain` 関数がリンク時に自動的に挿入されます。<br /><br /> DLL の起動コードをリンクします。<br /><br /> コマンド ラインでエクスポート \(.exp\) ファイルが指定されていない場合は、インポート ライブラリ \(.lib\) を作成します。  このインポート ライブラリを、DLL を呼び出すアプリケーションにリンクしてください。<br /><br /> [\/Fe \(EXE ファイルの名前の指定\)](../../build/reference/fe-name-exe-file.md) で指定したファイル名を、.exe ファイルではなく DLL の名前として解釈します。  既定では、プログラム名は *basename*.exe ではなく、*basename*.dll になります。<br /><br /> **\/MD** を明示的に指定している場合以外は、**\/MT** が暗黙に指定されます。|  
|**\/LDd**|デバッグ DLL を作成します。  `_MT` および `_DEBUG` を定義します。|  
  
 C ランタイム ライブラリ、および [\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md) を指定したコンパイルで使用されるライブラリの詳細については、「[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)」を参照してください。  
  
 リンカーの特定の呼び出しに渡されるすべてのモジュールは、同じランタイム ライブラリ コンパイラ オプション \(**\/MD**、**\/MT**、**\/LD**\) を指定してコンパイルされている必要があります。  
  
 デバッグ バージョンのランタイム ライブラリを使用する方法の詳細については、「[C ランタイム ライブラリ リファレンス](../../c-runtime-library/c-run-time-library-reference.md)」を参照してください。  
  
 サポート技術情報の「HOWTO: Link with the Correct C Run\-Time \(CRT\) Library \(Q140584\)」でも、適切な C ランタイム ライブラリの選択方法を説明しています。  
  
 DLL の詳細については、「[Visual C\+\+ の DLL](../../build/dlls-in-visual-cpp.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを展開します。  
  
3.  **\[コード生成\]** プロパティ ページを選択します。  
  
4.  **\[ランタイム ライブラリ\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeLibrary%2A> を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)