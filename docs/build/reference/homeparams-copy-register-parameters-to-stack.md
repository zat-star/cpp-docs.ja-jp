---
title: "/homeparams (レジスタ パラメーターのスタックへのコピー) | Microsoft Docs"
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
  - "/homeparams"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/homeparams コンパイラ オプション [C++]"
  - "-homeparams コンパイラ オプション [C++]"
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /homeparams (レジスタ パラメーターのスタックへのコピー)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

関数の実行に入ったときに、レジスタで渡されたパラメーターを、強制的にスタック内のその場所に書き込みます。  
  
## 構文  
  
```  
/homeparams  
```  
  
## 解説  
 これは、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)] コンパイラ \(ネイティブ コンパイルおよびクロス コンパイル\) だけで使用されるコンパイラ オプションです。  
  
 パラメーターが [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] コンパイルに渡されるときは、呼び出し規約によりパラメーター \(レジスタに渡されたパラメーターも含む\) 用のスタック空間が必要です。  詳細については、「[パラメーターの引き渡し](../../build/parameter-passing.md)」を参照してください。  ただしリリース ビルドの既定では、レジスタ パラメーターはスタックではなく、パラメーター用に既に指定されている空間に書き込まれます。  このことは、プログラムの最適化されたビルド \(リリース ビルド\) のデバッグを困難にします。  
  
 リリース ビルドでは、**\/homeparams** を使用して、アプリケーションを確実にデバッグできるようにしてください。  **\/homeparams** ではレジスタ パラメーターを繰り返しスタックに読み込む必要があるためパフォーマンスが低下します。  
  
 デバッグ ビルドでは、レジスタに渡されるパラメーターが常にスタックに読み込まれます。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  \[追加のオプション\]ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)