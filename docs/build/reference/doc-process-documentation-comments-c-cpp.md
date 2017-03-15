---
title: "/doc (ドキュメント コメントの処理) (C/C++) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles"
  - "/doc"
  - "VC.Project.VCCLCompilerTool.XMLDocumentationFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/doc コンパイラ オプション [C++]"
  - "コメント, C++ コード"
  - "-doc コンパイラ オプション [C++]"
  - "XML ドキュメント, コメント (ソース ファイルの)"
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /doc (ドキュメント コメントの処理) (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラが、ソース コード ファイル内のドキュメント コメントを処理し、ドキュメント コメントを含む各ソース コード ファイルの .xdc ファイルを作成します。  
  
## 構文  
  
```  
/doc[name]  
```  
  
## Arguments  
 `name`  
 コンパイラが作成する .xdc ファイルの名前。  コンパイルで .cpp ファイルが 1 つ渡される場合のみ有効です。  
  
## 解説  
 .xdc ファイルは、xdcmake.exe で処理され .xml ファイルに挿入されます。  詳細については、「[XDCMake リファレンス](../../ide/xdcmake-reference.md)」を参照してください。  
  
 ドキュメント コメントをソース コード ファイルに追加できます。  詳細については、「[ドキュメント コメント用の推奨タグ](../Topic/Recommended%20Tags%20for%20Documentation%20Comments%20\(Visual%20C++\).md)」を参照してください。  
  
 **\/doc** は **\/clr:oldSyntax** と互換性がありません。詳細については、「[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
 生成された .xml ファイルで IntelliSense 機能を使用するには、サポートするアセンブリの名前と .xml ファイル名を同じにして、そのファイルをアセンブリと同じディレクトリに置いてください。  アセンブリが Visual Studio プロジェクトで参照されると、.xml ファイルも検出されます。  詳細については、「[IntelliSense の使用方法](../Topic/Using%20IntelliSense.md)」および「[XML コード コメントの追加](../Topic/Supplying%20XML%20Code%20Comments.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[C\/C\+\+\]** ノードを展開します。  
  
4.  **\[出力ファイル\]** プロパティ ページをクリックします。  
  
5.  **\[XML ドキュメント ファイルの生成\]** プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)