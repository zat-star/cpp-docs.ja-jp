---
title: "C ランタイム エラー R6002 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6002"
ms.assetid: 8fbbe65a-9c43-459e-8342-e1f6d1cef7d0
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# C ランタイム エラー R6002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

floating\-point support not loaded  
  
 必要な浮動小数点ライブラリがリンクされていません。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  コプロセッサがインストールされていないコンピューター上で、コプロセッサを必要とするオプション \(\/FPi87 など\) を指定してプログラムをコンパイルおよびリンクしようとしています。  
  
2.  `printf_s` 関数や `scanf_s` 関数で使用される書式指定文字列に浮動小数点の書式指定が含まれていますが、プログラムには浮動小数点の値や変数が使用されていません。  
  
3.  コンパイラは、プログラムの大きさを最少にするために、必要な場合に限り、浮動小数点ルーチンを読み込みます。  この場合、書式指定文字列に浮動小数点の書式指定が検出されないと、コンパイラは必要な浮動小数点ルーチンを読み込みません。  
  
4.  書式指定文字列の浮動小数点の書式指定に対応する浮動小数点を引数に使用するか、プログラム中の任意の場所で浮動小数点値の代入ステートメントを実行してください。  これらの処理によって浮動小数点ルーチンが読み込まれます。  
  
5.  混合言語を使用したプログラムで、リンク時に、FORTRAN ライブラリよりも先に C ライブラリが指定されています。  C ライブラリを後に指定してリンクし直してください。