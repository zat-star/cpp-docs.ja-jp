---
title: "/Gy (関数レベルのリンクの有効化) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking"
  - "/gy"
  - "VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gy コンパイラ オプション [C++]"
  - "COMDAT 関数"
  - "有効化 (関数レベルのリンクを) コンパイラ オプション [C++]"
  - "Gy コンパイラ オプション [C++]"
  - "-Gy コンパイラ オプション [C++]"
  - "パッケージ化された関数"
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# /Gy (関数レベルのリンクの有効化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

各関数をパッケージ化された関数 \(COMDAT\) 形式でパッケージ化します。  
  
## 構文  
  
```  
/Gy[-]  
```  
  
## 解説  
 リンカーでは、DLL または .exe ファイルの各関数を除外したり順序付けたりするために、その関数を COMDAT として別にパッケージ化する必要があります。  
  
 リンカー オプションの [\/OPT \(最適化\)](../../build/reference/opt-optimizations.md) を指定すると、.exe ファイルから未参照のパッケージ化された関数が除外されます。  
  
 リンカー オプションの [\/ORDER \(関数の順序\)](../../build/reference/order-put-functions-in-order.md) を指定すると、パッケージ化された関数が指定された順序で .exe ファイルに含められます。  
  
 インライン関数は、呼び出しとしてインスタンス化される場合は \(たとえば、インライン化が無効な場合や関数のアドレスを取得する場合など\)、常にパッケージ化されます。  また、C\+\+ のクラス宣言内で定義されているメンバー関数は、自動的にパッケージ化されます。ただし、他の関数は自動的にはパッケージ化されないため、このオプションを指定してこれらの関数をパッケージ化します。  
  
> [!NOTE]
>  エディット コンティニュに対して [\/ZI](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) オプションを使用すると、**\/Gy** オプションが自動的に設定されます。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コード生成\]** プロパティ ページをクリックします。  
  
4.  **\[関数レベルでリンクする\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)