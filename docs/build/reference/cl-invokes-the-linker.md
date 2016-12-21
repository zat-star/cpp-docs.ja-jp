---
title: "リンカーを呼び出す CL | Microsoft Docs"
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
  - "cl.exe コンパイラ [C++], コンパイル (リンクなし)"
  - "cl.exe コンパイラ [C++], 制御 (リンカーを)"
  - "コンパイル (ソース コードを) [C++], リンクを使用しない"
  - "起動 (コンパイラからリンカーを)"
  - "LINK ツール [C++], 起動 (CL コンパイラから)"
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカーを呼び出す CL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CL では、\/c オプションを指定しない限り、コンパイル後に自動的にリンカーを起動します。  このとき、コンパイルによって生成された .obj ファイルの名前と、コマンド ラインで指定されたファイルの名前が CL からリンカーに渡されます。  リンカーは、環境変数 LINK で指定されたオプションを使います。  リンカーのオプションは、CL のコマンド ラインで \/link オプションを使って指定することもできます。  \/link オプションの後ろに指定されたオプションは、環境変数 LINK で指定されたオプションよりも優先されます。  次のオプションを指定すると、リンクが行われません。  
  
|オプション|説明|  
|-----------|--------|  
|\/c|コンパイルだけを行い、リンクは行いません。|  
|\/E、\/EP、\/P|プリプロセスだけを行い、コンパイルとリンクは行いません。|  
|\/Zg|関数プロトタイプを生成します。|  
|\/Zs|構文をチェックします。|  
  
 リンクの詳細については、「[リンカー オプション](../../build/reference/linker-options.md)」を参照してください。  
  
## 使用例  
 ここでは、MAIN.c、MOD1.c、および MOD2.c の 3 つの C ソース ファイルをコンパイルします。  各ファイルは、別のファイルで定義されている関数を呼び出します。  
  
-   MAIN.c は、MOD1.c に定義されている関数 `func1` と MOD2.c に定義されている関数 `func2` を呼び出します。  
  
-   MOD1.c は、標準ライブラリ関数 `printf_s` と `scanf_s` を呼び出します。  
  
-   MOD2.c は、ライブラリ MYGRAPH.lib に定義されているグラフィックス関数 `myline` と `mycircle` を呼び出します。  
  
 このプログラムをビルドするには、コマンド ラインで次のように指定してコンパイルします。  
  
```  
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib  
```  
  
 CL では、まず C ソース ファイルをコンパイルし、オブジェクト ファイル MAIN.obj、MOD1.obj、および MOD2.obj を生成します。  各 .obj ファイルには、標準ライブラリの名前が埋め込まれます。  詳細については、「[\/MD、\/ML、\/MT、\/LD \(ランタイム ライブラリの使用\)](../../build/reference/md-mt-ld-use-run-time-library.md)」を参照してください。  
  
 obj ファイルの名前は、ライブラリ名 MYGRAPH.lib と共に CL からリンカーに渡されます。  リンカーは、次のように外部参照を解決します。  
  
1.  MAIN.obj では、MOD1.obj 内の定義を使って `func1` への参照が解決され、MOD2.obj 内の定義を使って `func2` への参照が解決されます。  
  
2.  MOD1.obj では、標準ライブラリ内の定義を使って、`printf_s` と `scanf_s` への参照が解決されます。この標準ライブラリの名前は、CL によって MOD1.obj に埋め込まれています。  
  
3.  MOD2.obj では、MYGRAPH.lib 内の定義を使って、`myline` と `mycircle` への参照が解決されます。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)