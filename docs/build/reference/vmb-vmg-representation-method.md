---
title: "/vmb、/vmg (処理形式) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/vmb"
  - "/vmg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/vmb コンパイラ オプション [C++]"
  - "/vmg コンパイラ オプション [C++]"
  - "処理形式のコンパイラ オプション [C++]"
  - "vmb コンパイラ オプション [C++]"
  - "-vmb コンパイラ オプション [C++]"
  - "vmg コンパイラ オプション [C++]"
  - "-vmg コンパイラ オプション [C++]"
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /vmb、/vmg (処理形式)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

クラス メンバーを指すポインターをコンパイル時にどのように処理するかを指定します。  
  
 必ずクラスを定義してからそのクラスのメンバーへのポインターを宣言する場合は、**\/vmb** を選択します。  
  
 クラスを定義する前に、そのクラスのメンバーへのポインターを宣言する場合は、**\/vmg** を選択します。  このような順序で宣言するのは、互いに参照し合う 2 つの別のクラスにあるメンバーを定義する場合です。  2 つのクラスが互いに参照し合うときは必然的に、いずれか一方のクラスがそれを定義する以前に参照されます。  
  
## 構文  
  
```  
/vmb  
/vmg  
```  
  
## 解説  
 コード内で [pointers\_to\_members](../Topic/pointers_to_members.md) または [継承キーワード](../../cpp/inheritance-keywords.md) を使用して、ポインター表現を指定することもできます。  
  
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