---
title: ".sbr ファイルの作成 | Microsoft Docs"
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
  - ".sbr ファイル"
  - "BSCMAKE, 入力ファイル"
  - "ローカル シンボル (ブラウザー情報の)"
  - "SBR ファイル"
  - "ソース ブラウザー ファイル"
  - "シンボル"
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .sbr ファイルの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

BSCMAKE の入力ファイルは、.sbr ファイルです。  コンパイラでは、コンパイルされる各オブジェクト ファイル \(.obj\) で .sbr ファイルが作成されます。  ブラウザー情報ファイルをビルドまたは更新するときには、プロジェクトのすべての .sbr ファイルがディスクに配置されている必要があります。  
  
 .sbr ファイルを作成するときに、できる限りすべての情報を使用する場合には、[\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) を指定します。  
  
 ローカル シンボルを含まない .sbr ファイルを作成するときには、[\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md) を指定します。  .sbr ファイルにローカル シンボルが含まれている場合でも、BSCMAKE の [\/El オプション](../Topic/BSCMAKE%20Options.md)を使用して .bsc ファイルからローカル シンボルを省略できます。  
  
 .sbr ファイルは、完全コンパイルでなくても作成できます。  たとえば、コンパイラで \/Zs オプションを指定することで構文チェックを実行するときに、\/FR または \/Fr を指定すると、.sbr ファイルを生成できます。  
  
 あらかじめ .sbr ファイルをパックして参照しない定義を削除しておけば、ビルド処理はさらに効率的になります。  コンパイラでは、.sbr ファイルが自動的にパックされます。  
  
## 参照  
 [.bsc ファイルのビルド](../../build/reference/building-a-dot-bsc-file.md)