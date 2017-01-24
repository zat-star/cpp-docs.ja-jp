---
title: "コンパイラの警告 (レベル 3) C4635 | Microsoft Docs"
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
  - "C4635"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4635"
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 3) C4635
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

XML ドキュメント コメント対象: XML の形式が正しくありません: 理由  
  
 コンパイラは XML タグに何らかの問題を検出しました。  問題を修正して再コンパイルします  
  
 次の例では C4635 が生成されます。  
  
```  
// C4635.cpp // compile with: /doc /clr /W3 /c /// <summary> /// The contents of the folder have changed. /// <summary/>   // C4635 // try the following line instead // /// </summary> public ref class Test {};  
```  
  
 このサンプルの次の出力に注意してください: **'member' の終了タグが開始タグ 'summary' と一致しません。**  
  
 このサンプルの問題は、\<summary\> の終了タグが不完全で、コンパイラが \<summary\> 終了タグとして認識しないことです。  \<member\> タグは、\/doc のコンパイルごとに、コンパイラによって .xdc ファイルに埋め込まれます。  そのため、ここでの問題は、終了タグ \<\/member\> が、コンパイラが \<summary\> を処理する前の開始タグと一致しないことです。