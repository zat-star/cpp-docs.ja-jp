---
title: "リソース コンパイラの致命的なエラー RC1052 | Microsoft Docs"
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
  - "RC1052"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1052"
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リソース コンパイラの致命的なエラー RC1052
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラの制限: \#if または \#ifdef ブロックの入れ子のレベルが深すぎます。  
  
 プログラムが `#if` と `#ifdef` のディレクティブに許容される最大の入れ子レベルを超えました。  
  
 このエラーは、これらのプリプロセッサ ディレクティブを使用するインクルード ファイルによって発生することがあります。  
  
 この問題を解決するには、リソース ファイル内の、入れ子になっている `#if` と `#ifdef` ディレクティブの数を減らします。  リソース ファイルに含まれているヘッダー ファイルによって問題が発生している場合は、ヘッダー ファイル内の、入れ子になった `#if` と `#ifdef`ディレクティブの数を減らします。  これができない場合は、既存のヘッダー ファイルに対してプリプロセッサを実行して、新しいヘッダー ファイルを作成し、リソース ファイルに含めることを検討してください。  詳細については、[\/P \(プリプロセス出力のファイルへの書き込み\)](../../build/reference/p-preprocess-to-a-file.md) コンパイラ オプションを参照してください。