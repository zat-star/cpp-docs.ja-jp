---
title: "データの交換 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DDX (ダイアログ データ エクスチェンジ), プロパティ シート"
  - "交換 (プロパティ シートとデータを)"
  - "プロパティ シート, データ交換"
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# データの交換
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ほとんどのダイアログ ボックスと同様に、プロパティ シートとアプリケーション間でのデータの交換は、プロパティ シートの最も重要な関数の 1 つです。  ここでは、このタスクを実行する方法について説明します。  
  
 プロパティ シートとのデータ交換は実際にはプロパティ シートのプロパティ ページとのデータ交換のリレーションシップです。  プロパティ ページとのデータ交換の手順は [CPropertyPage](../mfc/reference/cpropertypage-class.md) オブジェクトは、[CDialog](../mfc/reference/cdialog-class.md) に特化されたオブジェクトであるため、ダイアログ ボックスとのデータ交換の場合と同じです。  プロシージャは、ダイアログ ボックスのコントロールとダイアログ ボックスのメンバー変数間のデータ交換がフレームワークのダイアログ データ エクスチェンジ \(DDX\) 機能を利用します。  
  
 プロパティ シートと通常のダイアログ ボックスとのデータ交換間の主な違いは、プロパティ シートに複数のページを持つため、プロパティ シートのすべてのページとのデータ交換です。  DDX の詳細については、「[ダイアログ データ エクスチェンジ \(DDX\) と検証](../mfc/dialog-data-exchange-and-validation.md)」を参照してください。  
  
 次の例では、プロパティ シートのビューに 2 ページ間のデータ交換を示します。:  
  
 [!code-cpp[NVC_MFCDocView#4](../mfc/codesnippet/CPP/exchanging-data_1.cpp)]  
  
## 参照  
 [プロパティ シート](../mfc/property-sheets-mfc.md)