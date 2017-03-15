---
title: "/Qimprecise_fwaits (try ブロック内部の fwaits を削除する) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Qimprecise_fwaits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Qimprecise_fwaits コンパイラ オプション (C++)"
  - "-Qimprecise_fwaits コンパイラ オプション (C++)"
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /Qimprecise_fwaits (try ブロック内部の fwaits を削除する)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/fp:except](../../build/reference/fp-specify-floating-point-behavior.md) コンパイラ オプションの使用時に、`try` ブロック内部の `fwait` を削除します。  
  
## 構文  
  
```  
/Qimprecise_fwaits  
```  
  
## 解説  
 **\/fp:except** も指定されていなければ、このオプションは無効です。  **\/fp:except** オプションを指定すると、コンパイラは `try` ブロックの中のコードの各行を囲む `fwait` コマンドを挿入します。  このようにして、コンパイラは例外が発生したコード行を特定できます。  **\/Qimprecise\_fwaits** は内部 `fwait` 命令を削除して、`try` ブロックを囲む待機だけを残します  これによってパフォーマンスは向上しますが、コンパイラはどの `try` ブロックで例外が発生したかは特定できますが、どの行かは特定できません。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [\/Q オプション \(低水準の操作\)](../../build/reference/q-options-low-level-operations.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)