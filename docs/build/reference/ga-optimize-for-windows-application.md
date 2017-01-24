---
title: "/GA (Windows アプリケーションの最適化) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication"
  - "/ga"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GA コンパイラ オプション [C++]"
  - "GA コンパイラ オプション [C++]"
  - "-GA コンパイラ オプション [C++]"
  - "最適化 (Windows アプリケーションを) コンパイラ オプション "
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GA (Windows アプリケーションの最適化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

より効率的にスレッド ローカル ストレージ \(TLS: Thread\-Local Storage\) の変数にアクセスできるようにコードが最適化されます。  
  
## 構文  
  
```  
/GA  
```  
  
## 解説  
 **\/GA** では、Windows ベースのプログラムで [\_\_declspec\(thread\)](../../cpp/declspec.md) を使って宣言されたデータへのアクセスを高速化します。  このオプションを設定すると、[\_\_tls\_index](http://msdn.microsoft.com/library/windows/desktop/ms686749) マクロが 0 と見なされます。  
  
 DLL に対して **\/GA** を使用すると、不適切なコードが生成されます。  
  
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