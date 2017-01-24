---
title: "独自のヘルパー関数の作成 | Microsoft Docs"
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
  - "ヘルパー関数"
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 独自のヘルパー関数の作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

独自のルーチンを作成すると、DLL またはインポートの名前に基づいて特定の処理を実行できます。  ルーチンの作成方法には、2 とおりあります。1 つは、提供されているコードに基づいて、独自のルーチンを記述する方法です。もう 1 つは、前に説明した通知フックを使用して、提供されているルーチンをフックする方法です。  
  
 独自のルーチンを記述する方法  
 提供されているコードを原型にして、新しいコードを簡単に作成できます。  この場合も、呼び出し規約に準拠します。リンカーが生成したサンクに制御を返す場合は、適切な関数ポインターを返す必要があります。  独自に作成したコードでは、自由に呼び出しを行い、呼び出しから抜けることができます。  
  
 処理開始通知フックを使用する方法  
 通知 dliStartProcessing で、既定のヘルパーと同じ値を受け取るユーザー定義の通知フック関数へのポインターを新しく設定するだけの簡単な方法です。  既定のヘルパーに制御が返されると、既定のヘルパーの以降の処理がすべてバイパスされるため、この時点で、フック関数を実質的に新しいヘルパー関数にすることができます。  
  
## 参照  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)