---
title: "コンパイラ エラー C2818 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2818"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2818"
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2818
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

オーバーロードされた演算子の「アプリケーションです\-\>' 型「型」の再帰的な  
  
 クラス メンバーに対するアクセス演算子の再定義に含まれている `return` ステートメントが再帰的です。  `->` 演算子の再定義で再帰的な処理を行うには、演算子のオーバーライド関数から呼び出される別の関数に再帰ルーチンを移動します。