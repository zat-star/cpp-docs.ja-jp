---
title: "2.7.2.2 firstprivate | Microsoft Docs"
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
ms.assetid: ece6ff12-2be1-4e4f-866c-d39345fd87b5
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.2 firstprivate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**firstprivate** の句は  **プライベート**  の句によって提供される機能のスーパーセットが用意されています。  **firstprivate** 句の構文は次のとおりです。:  
  
```  
firstprivate(variable-list)  
```  
  
 *変数*  の一覧で指定された変数に 25 ページ [セクション 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) に説明されているように  **プライベート**  句のセマンティクスがあります。  スレッドごとに一度行ったように初期化するコンストラクターが実行されます。スレッドの構造の実行前に発生します。  parallel コンストラクトの **firstprivate** の句では新しいプライベート オブジェクトの初期値はそのスレッドの parallel コンストラクト直前に元のオブジェクトの値です。  作業共有の構造体の **firstprivate** の句では実行するスレッドごとに新しいプライベート オブジェクトの初期値は作業共有の構造同じスレッドが共有作業の構造が発生する時点までに元のオブジェクトの値です。  またC\+\+ では各スレッドの新しいプライベート オブジェクトがオブジェクトから構築されたコピー元のオブジェクト。  
  
 **firstprivate** の句に制限 : は次のとおりです。  
  
-   **firstprivate** の句で指定された変数は不適切な型または参照型はありません。  
  
-   **firstprivate** にアクセスでき明確なコピー コンストラクターが必要であると指定されたクラス型の変数。  
  
-   並列領域内でプライベートにするか **並列**  のディレクティブの  **リダクション**  の句に表示される変数はparallel コンストラクトにバインドする共有作業のディレクティブで **firstprivate** の句で指定することはできません。