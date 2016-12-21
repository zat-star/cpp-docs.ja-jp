---
title: "/LN (MSIL モジュールの作成) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/LN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LN コンパイラ オプション [C++]"
  - "-LN コンパイラ オプション [C++]"
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /LN (MSIL モジュールの作成)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アセンブリ マニフェストを出力ファイルに挿入しません。  
  
## 構文  
  
```  
/LN  
```  
  
## 解説  
 既定では、アセンブリ マニフェストが出力ファイルに挿入され、**\/LN** は無効になっています。  
  
 **\/LN** を使用するときは、[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md) オプションのいずれか 1 つも使用する必要があります。  
  
 マニフェストにアセンブリ メタデータがないマネージ プログラムをモジュールと呼びます。  [\/c \(リンクを行わないコンパイル\)](../../build/reference/c-compile-without-linking.md) および **\/LN** を指定してコンパイルする場合は、リンカー フェースで [\/NOASSEMBLY \(MSIL モジュールの作成\)](../../build/reference/noassembly-create-a-msil-module.md) を指定して出力ファイルを作成します。  
  
 コンポーネント ベースの方法を使用してアセンブリをビルドする場合は、モジュールを作成できます。つまり、型を作成してモジュールにコンパイルした後、1 つ以上のモジュールからアセンブリを生成できます。モジュールからアセンブリを作成する方法の詳細については、「[リンカー入力としての .netmodule ファイル](../Topic/.netmodule%20Files%20as%20Linker%20Input.md)」または「[Al.exe \(アセンブリ リンカー\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)」を参照してください。  
  
 モジュールの既定のファイル拡張子は"です。  
  
 Visual C\+\+ 2005 より前の [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] リリースでは、モジュールは **\/clr:noAssembly** を指定して作成されました。  
  
 Visual C\+\+ リンカーは、入力、リンカーによって生成される出力ファイルはリンカーに渡された .netmodules のいずれかへの実行時に依存しないアセンブリまたは"であるため .netmodule ファイルをリンクできます。詳細については、「[リンカー入力としての .netmodule ファイル](../Topic/.netmodule%20Files%20as%20Linker%20Input.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
-   リンカー フェーズで [\/NOASSEMBLY \(MSIL モジュールの作成\)](../../build/reference/noassembly-create-a-msil-module.md) を指定して出力ファイルを作成します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   このコンパイラ オプションは、コードからは変更できません。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)