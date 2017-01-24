---
title: "/Yl (デバッグ ライブラリの PCH 参照の挿入) | Microsoft Docs"
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
  - "/yi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Yl コンパイラ オプション [C++]"
  - "Yl コンパイラ オプション [C++]"
  - "-Yl コンパイラ オプション [C++]"
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Yl (デバッグ ライブラリの PCH 参照の挿入)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プリコンパイル済みヘッダーを使用するデバッグ ライブラリの作成時にビルドが失敗する場合に使用されます。  
  
## 構文  
  
```  
/Ylsymbol  
```  
  
```  
/Yl-  
```  
  
## Arguments  
 `symbol`  
 オブジェクト モジュールに格納する任意のシンボル。  
  
 \-  
 明示的に **\/Yl** のコンパイラ オプションを無効にすると負符号 \(\-\)。  
  
## 解説  
 既定では、**\/Yl** コンパイラ オプション \(*symbol*の指定なし\)。  **\/Yl** オプションは、デバッガーが型に関する詳細な情報を得ることができます。  **\/Yl\-** は 既定の動作を無効にします。  
  
 **\/Yc** と **\/Yl**`symbol` を指定してモジュールをコンパイルすると、コンパイラによって \_\_@@\_PchSym\_@00@...@`symbol` のようなシンボルが作成されます。省略記号 \(...\) はリンカーによって生成される文字列です。このシンボルはオブジェクト モジュールに格納されます。  このプリコンパイル済みヘッダーを使用してコンパイルするソース ファイルは、指定したシンボルを参照します。このため、リンカーによりオブジェクト モジュールとライブラリからのデバッグ情報が組み込まれます。  
  
 このオプションを使用すると、LNK1211 が発生することがあります。  [\/Yc \(プリコンパイル済みヘッダー ファイルの作成\)](../../build/reference/yc-create-precompiled-header-file.md) オプションと [\/Z7、\/Zi、\/ZI \(デバッグ情報の形式\)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) オプションを指定すると、デバッグ情報が含まれたプリコンパイル済みヘッダー ファイルが作成されます。  プリコンパイル済みヘッダーをライブラリに格納し、ライブラリを使用してオブジェクト モジュールを構築するときに、ソース コードがプリコンパイル済みヘッダー ファイルに定義された関数を 1 つも参照しないと、エラーが起こります。  
  
 関数定義が含まれていないプリコンパイル済みヘッダー ファイルを作成するときに、**\/Yl**`symbol` を指定すると、問題を解決できます。ただし、`symbol` はライブラリ内の任意のシンボルの名前です。  このオプションは、デバッグ情報をプリコンパイル済みヘッダー情報に格納するようにコンパイラに指示します。  
  
 プリコンパイル済みヘッダーの詳細については、以下のトピックを参照してください。  
  
-   [\/Y \(プリコンパイル済みヘッダー\)](../../build/reference/y-precompiled-headers.md)  
  
-   [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)