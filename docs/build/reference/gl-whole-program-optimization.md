---
title: "/GL (プログラム全体の最適化) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/gl"
  - "VC.Project.VCCLWCECompilerTool.WholeProgramOptimization"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GL コンパイラ オプション [C++]"
  - "GL コンパイラ オプション [C++]"
  - "-GL コンパイラ オプション [C++]"
  - "プログラム全体の最適化と C++ コンパイラ"
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /GL (プログラム全体の最適化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラム全体の最適化を有効にします。  
  
## 構文  
  
```  
/GL[-]  
```  
  
## 解説  
 プログラム全体の最適化オプションを使用すると、プログラムのすべてのモジュールに関する情報を使用して最適化処理を実行できます。  プログラム全体の最適化オプションを使用しない場合は、各モジュール \(コンパイル単位\) ベースで最適化処理を実行します。  
  
 既定では、プログラム全体の最適化オプションは無効になっているため、明示的に有効にする必要があります。  ただし、**\/GL\-** を指定して明示的に無効にすることもできます。  
  
 すべてのモジュールの情報を使用すると、コンパイラでは次のことができます。  
  
-   関数境界にまたがってレジスタの使用を最適化します。  
  
-   グローバル データの変更の追跡ジョブを効率化し、読み込みおよび格納の回数を減らします。  
  
-   ポインターの逆参照によって変更される可能性のあるアイテム セットの追跡ジョブを効率化し、読み込みおよび格納の回数を減らします。  
  
-   関数定義が別のモジュールにある場合でも、モジュールの関数をインライン展開できます。  
  
 **\/GL** を使って生成された .obj ファイルは、[EDITBIN](../Topic/EDITBIN%20Reference.md) や [DUMPBIN](../../build/reference/dumpbin-reference.md) などのリンカー ユーティリティでは使用できません。  
  
 **\/GL** と [\/c](../../build/reference/c-compile-without-linking.md) を使ってプログラムをコンパイルする場合は、\/LTCG リンカー オプションを使用して出力ファイルを作成する必要があります。  
  
 [\/ZI](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) を **\/GL** と共に使用することはできません。  
  
 現在のバージョンで **\/GL** を使って生成されたファイル形式は、Visual C\+\+ の後続のバージョンでは読み取ることができない場合があります。  現在および将来においてユーザーが使用する Visual C\+\+ のすべてのバージョン用の .lib ファイルのコピーを同梱する意思がない場合は、**\/GL** を使って生成された .obj ファイルで構成された .lib ファイルを出荷しないでください。  
  
 **\/GL** の .obj ファイルを生成したときと同じコンピューターで .lib ファイルをリンクする場合以外は、**\/GL** とプリコンパイル済みヘッダー ファイルを使って生成された .obj ファイルを .lib ファイルのビルドに使用しないでください。  リンク時に、.obj ファイルのプリコンパイル済みヘッダー ファイルの情報が必要になります。  
  
 で使用できる最適化、プログラム全体の最適化の詳細については、「[\/LTCG](../../build/reference/ltcg-link-time-code-generation.md)」を参照してください。**\/GL** は、ガイド付き最適化のプロファイルも使用できるようにします。; \/LTCG を参照してください。ガイド付き最適化のプロファイルのコンパイル時に、ガイド付き最適化のプロファイルの関数順序を使用する場合は、[\/Gy](../../build/reference/gy-enable-function-level-linking.md) を使用するか、または \/Gy を暗黙に指定するコンパイラ オプションを使用して、コンパイルを実行する必要があります。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  開発環境で **\/GL** を指定する方法については、「[\/LTCG \(リンク時のコード生成\)](../../build/reference/ltcg-link-time-code-generation.md)」を参照してください。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)