---
title: "環境変数 CL | Microsoft Docs"
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
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe コンパイラ, 環境変数"
  - "環境変数, CL コンパイラ"
  - "INCLUDE 環境変数"
  - "LIBPATH 環境変数"
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 環境変数 CL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CL ツールでは、次の環境変数を使用します。  
  
-   CL と \_CL\_ \(定義されている場合\)。  CL ツールは、処理の前に、コマンド ライン引数の先頭に環境変数 CL に定義されているオプションと引数を追加し、\_CL\_ に定義されているオプションと引数をコマンド ライン引数の末尾に追加します。  
  
-   INCLUDE。Visual C\+\+ インストールの \\include サブディレクトリを示す必要があります。  
  
-   LIBPATH。[\#using](../../preprocessor/hash-using-directive-cpp.md) を使用して参照するメタデータ ファイルを検索するディレクトリを指定します。  LIBPATH の詳細については、`#using` の説明を参照してください。  
  
 CL または \_CL\_ 環境変数は、次の構文を使用して設定できます。  
  
```  
SET CL=[ [option] ... [file] ...] [/link link-opt ...]  
SET _CL_=[ [option] ... [file] ...] [/link link-opt ...]  
```  
  
 CL および \_CL\_ 環境変数の詳細については、「[コンパイラのコマンド ライン構文](../../build/reference/compiler-command-line-syntax.md)」を参照してください。  
  
 これらの環境変数を使用してよく使用するファイルやオプションを定義し、コマンド ラインを使用して特定用途向けの特定のファイルおよびオプションを定義できます。  CL および \_CL\_ 環境変数は、1,024 文字 \(コマンド ラインの入力の制限\) に制限されます。  
  
 \/D オプションを使用して等号 \(\=\) を使用するシンボルを定義することはできません。  等号の代わりにシャープ記号 \(\#\) を使用することができます。  このように、CL または \_CL\_ 環境変数を使用して、明示的な値を持つプリプロセッサ定数を定義できます \(たとえば、`DEBUG=1` を定義する `/DDEBUG#1`\)。  
  
 関連情報については、「[環境変数の設定](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)」を参照してください。  
  
## 使用例  
 CL 環境変数の設定例を次に示します。  
  
```  
SET CL=/Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ  
```  
  
 この環境変数が設定されているときにコマンド ラインで「`CL INPUT.C`」と入力した場合、次のコマンドは有効です。  
  
```  
CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ INPUT.C  
```  
  
 次の例では、単純な CL コマンドを実行すると、FILE1.c および FILE2.c の各ソース ファイルがコンパイルされ、FILE1.obj、FILE2.obj、および FILE3.obj の各オブジェクト ファイルがリンクされます。  
  
```  
SET CL=FILE1.C FILE2.C  
SET _CL_=FILE3.OBJ  
CL  
  
```  
  
 これは、次のコマンド ラインと同じ効果を持ちます。  
  
```  
CL FILE1.C FILE2.C FILE3.OBJ  
```  
  
## 参照  
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)