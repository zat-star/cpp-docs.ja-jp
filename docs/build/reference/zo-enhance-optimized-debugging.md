---
title: "/Zo (最適化されたデバッグ機能の強化) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "-Zo"
  - "/Zo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zo コンパイラ オプション [C++]"
  - "Zo コンパイラ オプション [C++]"
  - "-Zo コンパイラ オプション [C++]"
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /Zo (最適化されたデバッグ機能の強化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非デバッグ ビルドで最適化されたコードに関する拡張デバッグ情報を生成します。  
  
## 構文  
  
```cpp  
/Zo[-]  
```  
  
## 解説  
 **\/Zo** コンパイラ スイッチは、最適化されたコードに関する拡張デバッグ情報を生成します。  最適化では、ローカル変数にレジスターを使い、コードを並べ替え、ループをベクトル化し、関数呼び出しをインライン化することがあります。  これらの最適化により、ソース コードとコンパイル済みのオブジェクト コードの関係が不明瞭になる場合があります。  **\/Zo** スイッチは、ローカル変数とインライン関数に関する追加のデバッグ情報を生成するようコンパイラに指示します。  このスイッチを使用すると、最適化されたコードを Visual Studio デバッガーでステップ実行するときに **\[自動変数\]**、**\[ローカル\]**、**\[ウォッチ\]** ウィンドウに変数を表示します。  また、スタック トレースを有効にして、WinDBG デバッガーでインライン関数を表示します。  最適化が無効になっているデバッグ ビルド \([\/Od](../../build/reference/od-disable-debug.md)\) には、**\/Zo** の指定時に生成される追加のデバッグ情報は不要です。  **\/Zo** スイッチは、最適化をオンにしてリリースの構成をデバッグするのに使用します。  最適化スイッチの詳細については、「[\/O オプション \(コードの最適化\)](../../build/reference/o-options-optimize-code.md)」を参照してください。  デバッグ情報を **\/Zi** または **\/Z7** で指定している場合、Visual Studio 2015 では　**\/Zo** オプションが既定で有効になります。  このコンパイラ オプションを明示的に無効にする場合に **\/Zo\-** を指定します。  
  
 **\/Zo** スイッチは、Visual Studio 2013 更新プログラム 3 で使用可能で、ドキュメントに記載されなくなった **\/d2Zi\+** スイッチと置き換わるものです。  
  
### Visual Studio で \/Zo コンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]**、**\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **\[追加オプション\]** プロパティを変更して `/Zo` を組み込んでから、**\[OK\]** をクリックします。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## 参照  
 [\/O オプション \(コードの最適化\)](../../build/reference/o-options-optimize-code.md)   
 [\/Z7、\/Zi、\/ZI \(デバッグ情報の形式\)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)   
 [エディット コンティニュ](../Topic/Edit%20and%20Continue.md)