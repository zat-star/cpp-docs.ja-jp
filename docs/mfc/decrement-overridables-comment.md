---
title: "// Overridables コメント | Microsoft Docs"
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
  - "MFC ソース ファイル, Overridables コメント"
  - "Overridables コメント (MFC ソース ファイルの)"
  - "オーバーライド, Overridables コメント (MFC ソース ファイルの)"
ms.assetid: 8968dea5-0d94-451f-bcb2-991580e65ba2
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // Overridables コメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC のクラス宣言の `// Overridables` セクションでは、基本クラスの動作を変更する必要がある場合は、派生クラスでオーバーライドできる仮想関数が含まれています。  これは通常、厳密には必要ないが、" on "から始まってという名前です。  次の関数がオーバーライドされるように設計されており、種類の「callback」を実装するか、または「OnCreateclient 提供します」。通常、これらのメンバーが保護されます。  
  
 MFC 自体で、純粋仮想関数は、このセクションに配置されます。  C\+\+ の純粋仮想関数はフォームの一つです: 1  
  
 `virtual void OnDraw( ) = 0;`  
  
 クラスからサンプル `CStdioFile`リスティングで、[コメントの例](../mfc/an-example-of-the-comments.md)にリストがオーバーライド可能な関数セクションは含まれません。  **CDocument**を一方、リスト 10 個前後のオーバーライドできるなメンバー関数分類します。  
  
 一部のクラスでは、コメント `// Advanced Overridables`を参照することができます。  これらは、高度なプログラマのみをオーバーライドする必要のある関数です。  ほとんどの場合、それらをオーバーライドする必要はありません。  
  
> [!NOTE]
>  この記事で説明されている規則は、オートメーション \(以前の OLE オートメーションと呼ばれます\) メソッドとプロパティの場合、並行して、一般に機能します。  オートメーション メソッドは MFC 操作に似ています。  オートメーション プロパティは MFC 属性に似ています。  オートメーション イベント \(ActiveX コントロールで、OLE コントロールとして以前既知のサポート\) MFC のオーバーライドできるなメンバー関数とほぼ同じです。  
  
## 参照  
 [MFC ソース ファイルの利用](../Topic/Using%20the%20MFC%20Source%20Files.md)   
 [コメントの例](../mfc/an-example-of-the-comments.md)   
 [\/\/ Implementation コメント](../mfc/decrement-implementation-comment.md)   
 [\/\/ Constructors コメント](../mfc/decrement-constructors-comment.md)   
 [\/\/ Attributes コメント](../Topic/--%20Attributes%20Comment.md)   
 [\/\/ Operations コメント](../mfc/decrement-operations-comment.md)