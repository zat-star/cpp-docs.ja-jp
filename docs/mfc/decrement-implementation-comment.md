---
title: "// Implementation コメント | Microsoft Docs"
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
  - "コメント, Implementation コメント"
  - "コメント, MFC"
  - "Implementation コメント (MFC ソース ファイルの)"
  - "MFC ソース ファイル, Implementation コメント"
ms.assetid: 4d799c07-8e71-4a6b-90ab-8282d6ff48ce
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // Implementation コメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`// Implementation` セクションは、MFC クラス宣言の重要な部分です。  
  
 この独身警察官寄宿寮すべての実装の詳細をクリックします。  メンバー変数とメンバー関数も、このセクションで使用できます。  この行の下の内容は、MFC の将来のリリースで変更できます。  これを回避できない場合 `// Implementation` の行の下に詳細に依存しないようにしてください。  また、実装の行で宣言されたメンバーが実装がテクニカル ノートで説明したは文書化されていません。  基本クラスの仮想関数のオーバーライドは、セクションに関係なく基本クラスの関数を定義するこのセクションに関数をオーバーライドすることで基本クラスの実装の詳細と見なされるため、存在します。  通常、これらのメンバーは、常に保護されます。  
  
 `// Implementation` のコメントで宣言されたメンバーが **public**、`protected`、または `private`として宣言できる [コメントの例](../mfc/an-example-of-the-comments.md) の下に表示する `CStdioFile` からわかります。  将来、変更される可能性があるため、これらのメンバーを慎重に使用する必要があります。  **public** としてメンバー グループを宣言すると、クラス ライブラリの実装が正しく機能するようにする必要があります。  ただし、これは安全に、宣言されたメンバーが使用できることを意味しません。  
  
> [!NOTE]
>  `// Implementation` のコメントの上または下の残りの種類のコメントを見つける可能性があります。  どちらの場合も、そので宣言されたメンバーの種類を示します。  これらの `// Implementation` のコメントの下にある場合、メンバーが MFC の将来のバージョンで変更される可能性があることを想定する必要があります。  
  
## 参照  
 [MFC ソース ファイルの利用](../Topic/Using%20the%20MFC%20Source%20Files.md)   
 [コメントの例](../mfc/an-example-of-the-comments.md)   
 [\/\/ Constructors コメント](../mfc/decrement-constructors-comment.md)   
 [\/\/ Attributes コメント](../Topic/--%20Attributes%20Comment.md)   
 [\/\/ Operations コメント](../mfc/decrement-operations-comment.md)   
 [\/\/ Overridables コメント](../mfc/decrement-overridables-comment.md)