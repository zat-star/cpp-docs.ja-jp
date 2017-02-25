---
title: "レコード ビューの使用法 (MFC データ アクセス) | Microsoft Docs"
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
  - "レコード ビュー, カスタマイズ (既定のコードを)"
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# レコード ビューの使用法 (MFC データ アクセス)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、ウィザードで生成したレコード ビュー用の既定のコードをカスタマイズする一般的な方法について説明します。  通常、[フィルター](../data/odbc/recordset-filtering-records-odbc.md)または[パラメーター](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)を使用したレコードの選択条件の指定、レコードの[並べ替え](../data/odbc/recordset-sorting-records-odbc.md)、SQL ステートメントのカスタマイズが必要となります。  
  
 この情報は、[CRecordView](../mfc/reference/crecordview-class.md) \(ODBC\) と [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) \(DAO\) の両方に適用されます。  
  
 `CRecordView` または `CDaoRecordView` の使用方法は、[CFormView](../mfc/reference/cformview-class.md) の使用方法とほぼ同じです。  基本的には、レコード ビューを使用して、1 つのレコードセットのレコードを表示し、場合によっては更新します。  この他に、他のレコードセットも使用する方法については、「[レコード ビュー: セカンド レコードセットを利用してリスト ボックスを表示する方法](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)」を参照してください。  
  
## 参照  
 [レコード ビュー \(MFC データ アクセス\)](../data/record-views-mfc-data-access.md)   
 [ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)