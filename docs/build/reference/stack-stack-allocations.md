---
title: "/STACK (スタック割り当て) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.StackReserveSize"
  - "VC.Project.VCLinkerTool.StackCommitSize"
  - "/stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STACK リンカー オプション"
  - "-STACK リンカー オプション"
  - "メモリ割り当て制限、スタック"
  - "/STACK リンカー オプション"
  - "スタック、設定 (サイズの)"
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /STACK (スタック割り当て)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/STACK:reserve[,commit]  
```  
  
## 解説  
 \/STACK オプションは、スタックのサイズをバイト単位で指定します。  このオプションは、.exe ファイルのビルドだけに使用します。  
  
 `reserve` 値は、仮想メモリ内のスタック割り当ての合計サイズを指定します。  ARM、x86、および [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] コンピューターの場合、既定のスタック のサイズは 1 MB です。  
  
 `commit` は、オペレーティング システムによって解釈が異なります。  Windows WindowsRT では、一度に確保する物理メモリ量です。  仮想メモリがコミットされると、ページング ファイル内にメモリ空間が予約されます。  `commit` の値を大きく設定すると、アプリケーションに必要なスタック領域が増えたときに処理時間を節約できます。ただし、必要なメモリ量と起動時間が増えます。  ARM、x86、および [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] コンピューターの場合、既定のコミット値は 4 KB です。  
  
 引数 `reserve` と引数 `commit` の値は、10 進表記か C 言語表記で指定します。  
  
 別の方法としては、モジュール定義 \(.def\) ファイルの [STACKSIZE](../../build/reference/stacksize.md) ステートメントでスタックのサイズを設定することもできます。  両方を指定した場合、**STACKSIZE** はスタック割り当て \(\/STACK\) オプションよりも優先します。  [EDITBIN](../Topic/EDITBIN%20Reference.md) ツールを使用すると、.exe ファイルをビルドした後でスタック サイズを変更できます。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーを選択します。  
  
3.  **\[システム\]** プロパティ ページをクリックします。  
  
4.  次のいずれかのプロパティを変更します。  
  
    -   **\[スタックのコミット サイズ\]**  
  
    -   **\[スタックのサイズの設定\]**  
  
### このリンカーをコードから設定するには  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A> プロパティを参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)