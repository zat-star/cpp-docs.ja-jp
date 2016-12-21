---
title: "レコード スクロール コマンドに対するコマンド ハンドラー (MFC データ アクセス) | Microsoft Docs"
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
  - "レコードのスクロール [C++]"
  - "レコード ビュー [C++], スクロール"
  - "スクロール (レコードを)"
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# レコード スクロール コマンドに対するコマンド ハンドラー (MFC データ アクセス)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CRecordView](../mfc/reference/crecordview-class.md) クラスおよび [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) クラスには、次の標準コマンドに対する既定のコマンド処理が用意されています。  
  
-   **ID\_RECORD\_MOVE\_FIRST**  
  
-   **ID\_RECORD\_MOVE\_LAST**  
  
-   **ID\_RECORD\_MOVE\_NEXT**  
  
-   **ID\_RECORD\_MOVE\_PREV**  
  
 `CRecordView` クラスおよび `CDaoRecordView` クラスの `OnMove` メンバー関数が、4 つのすべてのコマンドに対する既定のコマンド処理であり、レコード間の移動を行います。  これらのコマンドが発行されると、RFX \(または DFX\) によってレコードセットのフィールドに新しいレコードが読み込まれ、DDX によってレコード フォームのコントロールに値が移動されます。  RFX については、「[レコード フィールド エクスチェンジ \(RFX\)](../data/odbc/record-field-exchange-rfx.md)」を参照してください。  
  
> [!NOTE]
>  標準的なレコード移動コマンドに関連付けられているユーザー インターフェイス オブジェクトには、必ずこれらの標準コマンド ID を使用してください。  
  
## 参照  
 [レコード ビュー内の移動](../Topic/Supporting%20Navigation%20in%20a%20Record%20View%20%20\(MFC%20Data%20Access\).md)