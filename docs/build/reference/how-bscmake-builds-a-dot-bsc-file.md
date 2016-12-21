---
title: "BSCMAKE による .bsc ファイルのビルド方法 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ブラウザー情報ファイル (.bsc), ビルド"
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE による .bsc ファイルのビルド方法
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

BSCMAKE では、.bsc ファイルのビルドまたはリビルドは、最も効率的な方法で行います。  問題の発生を防ぐには、ビルドのプロセスを理解しておくことが重要です。  
  
 BSCMAKE でブラウザー情報ファイルがビルドされるときに、.sbr ファイルは長さ 0 に切り捨てられます。  同じファイルの 2 回目以降のビルドでは、.sbr ファイルの長さが 0 \(つまり空\) であることによって、その .sbr ファイルに新しい情報がないことが BSCMAKE に示されます。  結果として BSCMAKE には、そのパートの更新が不要のためインクリメンタル ビルドで十分であることが示されます。  \/n オプションが指定されていない限り、BSCMAKE による各ビルドでは、変更されている .sbr ファイルだけを使用してインクリメンタル ビルド方式でファイルの更新が試されます。  
  
 BSCMAKE では、\/o オプションで指定された名前の .bsc ファイルが検索されます。  \/o が指定されていない場合は、最初の .sbr ファイル名と拡張子 .bsc を持つファイルが検索されます。  そのファイルが存在する場合は、情報を提供する .sbr ファイルだけを使用して、ブラウザー情報ファイルのインクリメンタル ビルドが実行されます。  ファイルが存在しない場合は、すべての .sbr ファイルを使用して完全ビルドが実行されます。  ビルドの規則は、以下のとおりです。  
  
-   完全ビルドが成功するための条件は、指定されたすべての .sbr ファイルが存在し、それらのファイルが切り捨てられていないということです。  .sbr ファイルが切り詰められている場合は、BSCMAKE を実行する前に再コンパイルまたはアセンブルによってそのファイルをリビルドする必要があります。  
  
-   インクリメンタル ビルドを成功させるための条件は、.bsc ファイルが必ず存在していることです。  また、空のファイルを含めて、情報を提供するすべての .sbr ファイルが存在し、それらすべてのファイルが BSCMAKE のコマンド ラインで指定されていることが必要です。  コマンド ラインで .sbr ファイルを省略すると、.bsc ファイルからそのファイルの情報が削除されます。  
  
## 参照  
 [.bsc ファイルのビルド](../../build/reference/building-a-dot-bsc-file.md)