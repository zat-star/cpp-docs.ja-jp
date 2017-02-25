---
title: "static ストレージ クラス指定子 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "静的ストレージ クラス指定子"
  - "静的変数, 指定子"
  - "ストレージ クラス, static"
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# static ストレージ クラス指定子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**static** のストレージ クラス指定子で内部レベルで宣言された変数には、グローバル有効期間がありますが、宣言されたブロック内でのみ表示されます。  定数文字列の場合、**static** を使用すると、頻繁に呼び出される関数で頻度の高い初期化のオーバーヘッドを軽減するのに役立ちます。  
  
## 解説  
 明示的に静的変数を初期化しない場合、既定で 0 に初期化されます。  関数内で、**static** はストレージを割り当てますが、定義として動作します。  内部静的変数は、1 つの関数にのみプライベートの永続ストレージ変数を提供します。  
  
## 参照  
 [スタティック](../misc/static-cpp.md)