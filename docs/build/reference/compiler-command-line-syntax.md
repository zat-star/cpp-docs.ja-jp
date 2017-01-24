---
title: "コンパイラ コマンド ラインの構文 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe コンパイラ, コマンド ライン構文"
  - "構文, CL コンパイラ コマンド ライン"
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ コマンド ラインの構文
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CL をコマンド ラインから起動するときは、次の構文でオプションとファイル名を指定します。  
  
```  
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]  
```  
  
 次の表は、コマンド ライン上の各エントリをまとめたものです。  
  
|エントリ|説明|  
|----------|--------|  
|*オプション*|1 つ以上の [CL オプション](../../build/reference/compiler-options.md)を指定します。  すべてのオプションは、指定されたすべてのソース ファイルに適用されます。  オプションは、スラッシュ \(\/\) またはダッシュ \(\-\) で指定します。  引数を取るオプションには、オプションと引数との間にスペースを挿入できるものと、挿入できないものとがあります。スペースを挿入できるかどうかは、各オプションの説明を参照してください。  \/HELP オプション以外のオプション名では、大文字と小文字が区別されます。  詳細については、「[CL オプションの指定順序](../../build/reference/order-of-cl-options.md)」を参照してください。|  
|`file`|ソース ファイル、.obj ファイル、ライブラリのいずれかの名前を指定します。  CL はソース ファイルをコンパイルし、.obj ファイルとライブラリの名前をリンカーに渡します。  詳細については、「[CL ファイル名の構文](../../build/reference/cl-filename-syntax.md)」を参照してください。|  
|*lib*|1 つ以上のライブラリ名を指定します。  このライブラリ名はリンカーに渡されます。|  
|*command\-file*|複数のオプションをファイル名を含むファイルを指定します。  詳細については、「[CL のコマンド ファイル](../../build/reference/cl-command-files.md)」を参照してください。|  
|*link\-opt*|1 つ以上の[リンカー オプション](../../build/reference/linker-options.md)を指定します。  指定したオプションはリンカーに渡されます。|  
  
 コマンド ラインの長さは、オペレーティング システムによって最大 1,024 文字に制限されています。この制限を超えない限り、オプション、ファイル名、ライブラリ名をいくつでも指定できます。  
  
 cl.exe の戻り値については、「[cl.exe の戻り値](../../build/reference/return-value-of-cl-exe.md)」を参照してください。  
  
> [!NOTE]
>  コマンド ライン入力の上限値 1,024 文字は、将来的に Windows で変更されることがあります。  
  
## 参照  
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)