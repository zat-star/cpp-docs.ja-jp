---
title: "2.7.2.1 private | Microsoft Docs"
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
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.1 private
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`private` の句によってチームの各スレッドに対してプライベートで変数リストの変数を宣言します。  `private` 句の構文は次のとおりです。:  
  
```  
private(variable-list)  
```  
  
 `private` の句で指定された変数の動作は次のとおりです。  自動保存の実行中に新しいオブジェクトが構造体のようになりました。  新しいオブジェクトのサイズと位置は変数の型によって決まります。  この割り当てはチームのスレッドに一度だけ実行され既定のコンストラクターはクラスのオブジェクトは必要に応じて ; 呼び出されます は初期値は不確定です。  変数で参照される構造体へ元のオブジェクトはエントリ絶対に必要に値を動的構造体のスコープ内で変更がない場合でも構造から終了時に不定な値があります。  
  
 ディレクティブの構文構造体の範囲変数ではスレッドによって割り当てられた新しいプライベート オブジェクト。  
  
 `private` の句に制限 : は次のとおりです。  
  
-   `private` の句で指定されたクラス型の変数でアクセスできるように明確な既定のコンストラクターが必要です。  
  
-   `private` の句で指定された変数は `mutable` のメンバーを持つクラス型を持たない  **定数** \- 修飾された型にはありません。  
  
-   `private` の句で指定された変数は不適切な型または参照型はありません。  
  
-   **並列**  のディレクティブの `reduction` の句に表示される変数はparallel コンストラクトにバインドする共有作業のディレクティブで `private` の句で指定することはできません。