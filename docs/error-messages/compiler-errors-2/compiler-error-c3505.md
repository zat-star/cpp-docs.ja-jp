---
title: "コンパイラ エラー C3505 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3505"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3505"
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3505
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

タイプライブラリ 'guid' を読み込めません。  
  
 C3505 は、64 ビット コンピューター上で \(32 ビットから\) 64 ビットのクロス コンパイラを実行している場合に、コンパイラが WOW64 で動作し、読み取りできるのが 32 ビット レジストリ ハイブからだけであることによって発生することがあります。  
  
 この C3505 は、インポートするタイプ ライブラリの 32 ビット バージョンと 64 ビット バージョンをビルドし、両方を登録することによって解決できます。または、ネイティブな 64 ビット コンパイラを使用できますが、その場合は、64 ビット コンパイラをポイントするように、IDE の VC\+\+ ディレクトリを変更することが必要です。  
  
 詳細については、次のトピックを参照してください。  
  
-   [方法: 64 ビットの Visual C\+\+ ツールセットをコマンド ラインから有効にする](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)  
  
-   [方法: 64 ビットの Visual C\+\+ ツールセットをコマンド ラインから有効にする](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)  
  
-   [方法 : Visual C\+\+ プロジェクトを 64 ビット プラットフォーム用に設定する](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)