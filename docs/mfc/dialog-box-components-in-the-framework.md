---
title: "フレームワークのダイアログ ボックス コンポーネント | Microsoft Docs"
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
  - "ダイアログ クラス, ダイアログ ボックス コンポーネント"
  - "ダイアログ テンプレート, MFC フレームワーク"
  - "MFC ダイアログ ボックス, MFC ダイアログ ボックスの概要"
  - "MFC ダイアログ ボックス, 作成"
  - "MFC ダイアログ ボックス, ダイアログ リソース"
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# フレームワークのダイアログ ボックス コンポーネント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

フレームワークのダイアログ ボックスは、次の 2 種類のコンポーネントがあります:  
  
-   ダイアログ ボックスのコントロールの配置を指定するダイアログ テンプレート リソース。  
  
     ダイアログ リソースには、Windows がダイアログ ウィンドウを作成および表示するダイアログ テンプレートを格納します。  テンプレートは、ダイアログ ボックスの特性を、ダイアログ ボックスのコントロールのサイズ、位置、スタイルと型と位置指定します。  通常、リソースとして格納されているダイアログ テンプレートを使用して、メモリ内で独自のテンプレートを作成できます。  
  
-   ダイアログ クラス、[CDialog](../mfc/reference/cdialog-class.md)から派生、プログラム インターフェイスをダイアログ ボックスを管理するために使用します。  
  
     ダイアログ ボックスが表示されたら、ウィンドウのウィンドウに接続されます。  ダイアログ ウィンドウが作成されると、ダイアログ テンプレート リソースがダイアログ ボックスの子ウィンドウのコントロールを作成するためのテンプレートとして使用されます。  
  
## 参照  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)