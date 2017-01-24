---
title: "// Operations コメント | Microsoft Docs"
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
  - "コメント, MFC"
  - "MFC ソース ファイル, Operations コメント"
  - "Operations コメント (MFC ソース ファイルの)"
ms.assetid: f3bff48d-26be-4db6-8435-9e4d079838c9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // Operations コメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC のクラス宣言の `// Operations` セクションが実行を行うために、オブジェクトにするか、物事が実行するアクションを呼び出すことができるメンバー関数を含む \(\) 操作を実行します。  これらの関数は、通常副作用があるため、通常は非**const** です。  そのクラスでの必要に応じて、仮想メソッドまたは仮想である場合があります。  通常、これらのメンバーはパブリックです。  
  
 クラスからサンプル `CStdioFile`リスティングで、[コメントの例](../mfc/an-example-of-the-comments.md)にリストはこのコメントの下に、2 種類のメンバー関数があります: `ReadString` と `WriteString`。  
  
 属性と同様に、さらに細分化できます。  
  
## 参照  
 [MFC ソース ファイルの利用](../Topic/Using%20the%20MFC%20Source%20Files.md)   
 [コメントの例](../mfc/an-example-of-the-comments.md)   
 [\/\/ Implementation コメント](../mfc/decrement-implementation-comment.md)   
 [\/\/ Constructors コメント](../mfc/decrement-constructors-comment.md)   
 [\/\/ Attributes コメント](../Topic/--%20Attributes%20Comment.md)   
 [\/\/ Overridables コメント](../mfc/decrement-overridables-comment.md)