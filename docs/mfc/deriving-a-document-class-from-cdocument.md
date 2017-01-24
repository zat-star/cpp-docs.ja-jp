---
title: "CDocument からのドキュメント クラスの派生 | Microsoft Docs"
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
  - "CDocument クラス, 派生"
  - "クラス [C++], 派生 (CDocument から)"
  - "派生クラス, 関数 (オーバーライドされる)"
  - "ドキュメント クラス, 関数 (オーバーライドされる)"
  - "ドキュメント オブジェクト, 派生"
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDocument からのドキュメント クラスの派生
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ドキュメントは、アプリケーションのデータを格納および管理します。  MFC アプリケーションを使用するには、ドキュメント クラス、以下を行う必要があります。指定された:ウィザード  
  
-   ドキュメントの種類の **CDocument** からクラスを派生してください。  
  
-   各ドキュメントにデータを格納するメンバー変数を追加します。  
  
-   ドキュメント クラスのオーバーライド **CDocument**`Serialize` のメンバー関数。  `Serialize` は ディスクに対するドキュメント データを読み書きします。  
  
## もう一つは、オーバーライドされる関数について説明します。  
 また **CDocument** の他のメンバー関数をオーバーライドする必要があります。  特に、動的に割り当てられたデータを破棄するには、ドキュメントのデータ メンバーと [DeleteContents](../Topic/CDocument::DeleteContents.md) を初期化するようにように [OnNewDocument](../Topic/CDocument::OnNewDocument.md) と [OnOpenDocument](../Topic/CDocument::OnOpenDocument.md) をオーバーライドする必要があります。  オーバーライドできるなメンバーについては、*" MFC リファレンス"*の [CDocument](../Topic/CDocument%20Class.md) クラスを参照してください。  
  
## 参照  
 [ドキュメントの使い方](../mfc/using-documents.md)