---
title: "CObject の使い方 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObject クラス"
  - "派生クラス, CObject から"
  - "例 [MFC], CObject"
  - "MFC, 基本クラス"
  - "ルート基本クラス (MFC の)"
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CObject の使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CObject](../Topic/CObject%20Class.md) は Microsoft Foundation Class ライブラリ \(MFC\) のほとんどのルート基本クラスです。  `CObject` クラスは、独自のプログラム オブジェクトに、シリアル化のサポートなど、ランタイム クラス情報組み込みことができ、する診断出力に表示できる便利な機能を備えています。  `CObject`からクラスを派生すれば、`CObject` クラスは、これらの機能を開発できます。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [CObject からクラスを派生してください。](../mfc/deriving-a-class-from-cobject.md)  
  
-   [My の派生クラスのランタイム クラス情報、動的生成およびシリアル化のサポートを追加します。](../mfc/specifying-levels-of-functionality.md)  
  
-   [ランタイム クラス情報にアクセスします。](../mfc/accessing-run-time-class-information.md)  
  
-   [オブジェクトを動的に作成します。](../Topic/Dynamic%20Object%20Creation.md)  
  
-   [オブジェクトのデータを診断用にダンプします。](http://msdn.microsoft.com/ja-jp/727855b1-5a83-44bd-9fe3-f1d535584b59)  
  
-   オブジェクトの内部状態を検証します \([MFC ASSERT\_VALID および CObject::AssertValid](http://msdn.microsoft.com/ja-jp/7654fb75-9e9a-499a-8165-0a96faf2d5e6)を参照してください\)。  
  
-   [永続ストレージにクラスのシリアル化する自体を持ちます。](../Topic/Serialization%20in%20MFC.md)  
  
-   [CObject のよく寄せられる質問](../mfc/cobject-class-frequently-asked-questions.md)の一覧を参照してください。  
  
## 参照  
 [概念](../mfc/mfc-concepts.md)   
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)   
 [CRuntimeClass 構造体](../Topic/CRuntimeClass%20Structure.md)   
 [ファイル](../mfc/files-in-mfc.md)   
 [シリアル化](../Topic/Serialization%20in%20MFC.md)