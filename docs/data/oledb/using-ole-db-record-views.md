---
title: "OLE DB レコード ビューの使用 | Microsoft Docs"
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
  - "COleDBRecordView クラス, 概要"
  - "MFC, レコード ビュー"
  - "OLE DB レコード ビュー"
  - "OLE DB, レコード ビュー"
  - "レコード ビュー, レコード ビュー オブジェクト"
  - "行セット, レコード ビュー"
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB レコード ビューの使用
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC アプリケーションで OLE DB の行セット データを表示する場合は、MFC の [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md) クラスを使用する必要があります。  `COleDBRecordView` から作成されたレコード ビュー オブジェクトにより、MFC コントロールにデータベース レコードを表示できます。  レコード ビューは、`CRowset` テンプレート クラスから作成された OLE DB 行セット オブジェクトに直接接続されている、ダイアログ形式のビューです。  行セット オブジェクトへのハンドルは簡単に取得できます。  
  
```  
COleDBRecordView myRecordView;  
...  
// CProductAccessor is a user record class  
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();  
```  
  
 ビューでは、ダイアログのコントロールに `CRowset` オブジェクトのフィールドが表示されます。  `COleDBRecordView` オブジェクトは、ダイアログ データ エクスチェンジ \(DDX: Dialog Data Exchange\)、および `CRowset`\> に組み込まれた移動機能 \(**MoveFirst**、`MoveNext`、`MovePrev`、および `MoveLast`\) を使用して、フォーム上のコントロールと行セットのフィールド間でのデータの移動を自動化します。  `COleDBRecordView` は、行セット内でのユーザーの位置を追跡し、レコード ビューがユーザー インターフェイスを更新できるようにします。また、別のレコードに移動する前に現在のレコードを更新する [OnMove](../Topic/COleDBRecordView::OnMove.md) メソッドを提供します。  
  
 **COleDbRecordView** で DDX 関数を使用して、データベース レコードセットから直接データを取得し、ダイアログ コントロールに表示できます。  **COleDbRecordView** では、**DDX\_Field\*** 関数 \(`DDX_FieldText` など\) ではなく、**DDX\_\*** メソッド \(`DDX_Text` など\) を使用する必要があります。  
  
## 参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)   
 [COleDBRecordView クラス](../../mfc/reference/coledbrecordview-class.md)