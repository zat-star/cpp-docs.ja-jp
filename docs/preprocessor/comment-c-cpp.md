---
title: "コメント (C/C++) | Microsoft Docs"
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
  - "vc-pragma.comment"
  - "comment_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "注釈 [C++]"
  - "comment プラグマ"
  - "コメント [C++], コンパイル済みファイル"
  - "プラグマ, コメント"
ms.assetid: 20f099ff-6303-49b3-9c03-a94b6aa69b85
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コメント (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オブジェクト ファイルまたは実行可能ファイル内にコメント レコードを配置します。  
  
## 構文  
  
```  
  
#pragma comment( comment-type [,"commentstring"] )  
```  
  
## 解説  
 *comment\-type* は、コメント レコードの種類を指定する定義済み識別子 \(後述\) の 1 つです。  省略可能な `commentstring` は、いくつかのコメントの種類で追加情報を指定する文字列リテラルです。  `commentstring` は文字列リテラルであるため、エスケープ文字、埋め込まれた引用符 \(**"**\)、および連結に関して、文字列リテラルのすべての規則に従います。  
  
 **compiler**  
 オブジェクト ファイル内にコンパイラの名前とバージョン番号を配置します。  このコメント レコードはリンカーには無視されます。  このレコードの種類で `commentstring` パラメーターを指定すると、コンパイラが警告を生成します。  
  
 **exestr**  
 オブジェクト ファイル内に `commentstring` を配置します。  リンク時に、この文字列は実行可能ファイルに配置されます。  実行可能ファイルが読み込まれるとき、この文字列はメモリには読み込まれません。ただし、ファイル内の出力可能文字列を検出するプログラムで検出できます。  このコメント レコードの種類の使用方法の 1 つは、実行可能ファイルにバージョン番号や同様の情報を埋め込むことです。  
  
 `exestr` の使用は推奨されておらず、将来のリリースで削除されます。リンカーは、このコメント レコードを処理しません。  
  
 **lib**  
 オブジェクト ファイル内にライブラリ検索レコードを配置します。  このコメントの種類では、リンカーで検索するライブラリの名前 \(および場合によってはパス\) を含む `commentstring` パラメーターを指定する必要があります。  オブジェクト ファイルでは既定のライブラリ検索レコードの後にライブラリ名が続きます。リンカーは、ライブラリが [\/nodefaultlib](../build/reference/nodefaultlib-ignore-libraries.md) で指定されない限り、コマンド ラインで名前を指定したときと同様にこのライブラリを検索します。  同じソース ファイルに複数のライブラリ検索レコードを配置できます。各レコードは、ソース ファイルで見つかった順序と同じ順序でオブジェクト ファイルに出現します。  
  
 既定のライブラリおよび追加されたライブラリの順序が重要な場合、[\/Zl](../build/reference/zl-omit-default-library-name.md) スイッチを付けてコンパイルすると、既定のライブラリ名はオブジェクト モジュールに取り込まれません。  2 つ目の comment プラグマを使用して、追加したライブラリの後に既定のライブラリの名前を挿入することができます。  これらのプラグマを使用して指定したライブラリは、ソース コードと同じ順序でオブジェクト モジュールに出現します。  
  
 **linker**  
 オブジェクト ファイル内に[リンカー オプション](../build/reference/linker-options.md)を配置します。  このコメントの種類を使用して、コマンド ラインに渡す代わりにリンカー オプションを指定するか、開発環境でリンカー オプションを指定することができます。  たとえば、\/include オプションを指定して、強制的にシンボルを追加できます。  
  
```  
#pragma comment(linker, "/include:__mySymbol")  
```  
  
 linker 識別子に渡すことができるのは、次の \(*comment\-type*\) リンカー オプションだけです。  
  
-   [\/DEFAULTLIB](../build/reference/defaultlib-specify-default-library.md)  
  
-   [\/EXPORT](../build/reference/export-exports-a-function.md)  
  
-   [\/INCLUDE](../build/reference/include-force-symbol-references.md)  
  
-   [\/MANIFESTDEPENDENCY](../build/reference/manifestdependency-specify-manifest-dependencies.md)  
  
-   [\/MERGE](../build/reference/merge-combine-sections.md)  
  
-   [\/SECTION](../build/reference/section-specify-section-attributes.md)  
  
 **user**  
 オブジェクト ファイル内に一般的なコメントを配置します。  `commentstring` パラメーターで、コメントのテキストを指定します。  このコメント レコードはリンカーには無視されます。  
  
 次のプラグマを指定すると、リンカーはリンク中に EMAPI.LIB ライブラリを探します。  リンカーは、まず現在の作業ディレクトリ内を検索し、次に LIB 環境変数で指定されたパス内を検索します。  
  
```  
#pragma comment( lib, "emapi" )  
```  
  
 次のプラグマを指定すると、コンパイラはオブジェクト ファイル内にコンパイラの名前とバージョン番号を埋め込みます。  
  
```  
#pragma comment( compiler )  
```  
  
> [!NOTE]
>  `commentstring` パラメーターを受け取るコメントの場合、マクロが文字列リテラルに展開されるのであれば、文字列リテラルを使用するどの場所でもそのマクロを使用できます。  文字列リテラルと、文字列リテラルに展開されるマクロとの任意の組み合わせを連結することもできます。  たとえば、次のステートメントは許容されます。  
  
```  
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )   
```  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)