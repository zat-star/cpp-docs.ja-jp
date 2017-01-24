---
title: "// Constructors コメント | Microsoft Docs"
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
  - "コメント, Constructors コメント"
  - "コメント, MFC"
  - "コンストラクター [C++], 宣言"
  - "Constructors コメント"
  - "宣言, コンストラクター"
  - "宣言 (コンストラクターを), コードのコメント"
  - "インスタンス コンストラクター, コードのコメント"
  - "MFC ソース ファイル, Constructors コメント"
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // Constructors コメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC のクラス宣言の `// Constructors` セクションはコンストラクター \(C\+\+ で\)、実際にオブジェクトを使用するために必要な初期化関数を宣言します。  たとえば、`CWnd::Create` はコンストラクター セクションに `CWnd` オブジェクトを使用する前に、まず C\+\+ のコンストラクターを呼び出すと **作成** 関数を呼び出して「完全に」構築する必要があるためです。  通常、これらのメンバーはパブリックです。  
  
 たとえば、`CStdioFile` に 3 個のコンストラクターが、そのうちの一つのクラスは [コメントの例](../mfc/an-example-of-the-comments.md)のリスティングに示します。  
  
## 参照  
 [MFC ソース ファイルの利用](../Topic/Using%20the%20MFC%20Source%20Files.md)   
 [\/\/ Implementation コメント](../mfc/decrement-implementation-comment.md)   
 [\/\/ Attributes コメント](../Topic/--%20Attributes%20Comment.md)   
 [\/\/ Operations コメント](../mfc/decrement-operations-comment.md)   
 [\/\/ Overridables コメント](../mfc/decrement-overridables-comment.md)