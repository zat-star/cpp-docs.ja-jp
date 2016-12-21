---
title: "コンパイラの警告 (レベル 1 および 4) C4115 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4115"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4115"
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1 および 4) C4115
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': かっこの中で名前付きの型が使用されました  
  
 構造体、共用体、または列挙型を定義するための特定のシンボルが、かっこで囲まれた式の内部で定義されています。 定義のスコープが、予期せぬものとなる場合があります。  
  
 C の関数呼び出しでは、定義はグローバル スコープを持ちます。 C\+\+ の呼び出しでは、定義は呼び出される関数と同じスコープを持ちます。  
  
 この警告は、かっこで囲まれた式ではない \(プロトタイプなど\) のかっこ内の宣言子によって引き起こされる場合もあります。  
  
 これは、ANSI 互換 \(\/Za\) でコンパイルされた C\+\+ プログラムと C プログラムではレベル 1 の警告です。 それ以外の場合はレベル 3 です。