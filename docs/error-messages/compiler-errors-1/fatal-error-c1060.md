---
title: "致命的なエラー C1060 | Microsoft Docs"
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
  - "C1060"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1060"
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1060
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ヒープの領域を使い果たしました。  
  
 オペレーティング システムまたはランタイム ライブラリがメモリの要求に対応できません。  
  
### このエラーを解決するには次の方法があります。  
  
1.  コンパイラによってエラー [C1076](../Topic/Fatal%20Error%20C1076.md) および [C3859](../Topic/Compiler%20Error%20C3859.md) も発行される場合は、[\/Zm](../Topic/-Zm%20\(Specify%20Precompiled%20Header%20Memory%20Allocation%20Limit\).md) コンパイラ オプションを使用して、メモリの割り当て制限を低減します。  残りのメモリ割り当てを削減すると、アプリケーションに使用できるヒープ領域が増加します。  
  
     [\/Zm](../Topic/-Zm%20\(Specify%20Precompiled%20Header%20Memory%20Allocation%20Limit\).md) オプションが既に設定されている場合は、削除してください。  オプションで指定されたメモリ割り当て制限が高すぎるために、ヒープ領域が足りなくなっている可能性があります。  [\/Zm](../Topic/-Zm%20\(Specify%20Precompiled%20Header%20Memory%20Allocation%20Limit\).md) オプションを削除すると、既定の制限がコンパイラによって使用されます。  
  
2.  64 ビット プラットフォームでコンパイルする場合は、64 ビットのコンパイラ ツールセットを使用します。  詳細については、「[方法: 64 ビットの Visual C\+\+ ツールセットをコマンド ラインから有効にする](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)」を参照してください。  
  
3.  32 ビットの Windows では、[3 GB](http://go.microsoft.com/fwlink/?LinkId=177831) の boot.ini スイッチを使用してみてください。  
  
4.  Windows のスワップ ファイルのサイズを大きくします。  
  
5.  実行中のプログラムを終了します。  
  
6.  不必要なインクルード ファイルを除去します。  
  
7.  不要なグローバル変数を削除します。これを行うには、たとえば、サイズの大きな配列を宣言する代わりに、メモリを動的に割り当てます。  
  
8.  不要な宣言を削除します。  
  
9. 現在のファイルを小さなファイルに分割します。