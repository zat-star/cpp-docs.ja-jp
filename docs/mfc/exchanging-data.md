---
title: "データを交換する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- property sheets [MFC], data exchange
- exchanging data with property sheets [MFC]
- DDX (dialog data exchange) [MFC], property sheets
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 172b03278ceede44f06b846c8b4f066e9f141e3b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exchanging-data"></a>データの交換
ほとんどのダイアログ ボックスと同様、プロパティ シートとアプリケーション間でデータの交換はプロパティ シートの最も重要な機能の 1 つです。 この記事では、このタスクを実行する方法について説明します。  
  
 プロパティ シートを使用してデータを交換するには実際にプロパティ シートの各プロパティ ページを使用してデータを交換します。 プロパティ ページを使用してデータを交換するための手順は、同じ ダイアログ ボックスでは、データを交換するので、 [CPropertyPage](../mfc/reference/cpropertypage-class.md)オブジェクトがだけ、特殊な[CDialog](../mfc/reference/cdialog-class.md)オブジェクト。 プロシージャでは、ダイアログ ボックスのオブジェクトのダイアログ ボックスとメンバー変数内のコントロール間のデータを交換するフレームワークのダイアログ データ エクス (チェンジ DDX) 機能を活用します。  
  
 プロパティ シートを含む、通常のダイアログ ボックスを使用してデータを交換する重要な違いは、プロパティ シート、複数のページのため、プロパティ シートのすべてのページを使用してデータを交換する必要があります。 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../mfc/dialog-data-exchange-and-validation.md)です。  
  
 次の例では、ビューとプロパティ シートの 2 つのページ間で交換するデータを示します。  
  
 [!code-cpp[NVC_MFCDocView#4](../mfc/codesnippet/cpp/exchanging-data_1.cpp)]  
  
## <a name="see-also"></a>参照  
 [プロパティ シート](../mfc/property-sheets-mfc.md)

