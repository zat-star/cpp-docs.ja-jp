---
title: "日時指定コントロールでのカスタム書式指定文字列の使い方 | Microsoft Docs"
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
  - "CDateTimeCtrl クラス, 表示スタイル"
  - "DateTimePicker コントロール [MFC]"
  - "DateTimePicker コントロール [MFC], 表示スタイル"
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 日時指定コントロールでのカスタム書式指定文字列の使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

既定で、日時指定のコントロールは、現在の日付を表示するための 3 種類の形式の種類 \(一意のスタイルに対応する各形式\) を指定するか、タイムアウトします:  
  
-   **DTS\_LONGDATEFORMAT**は長い形式の日付を表示し、「Wednesday などの出力を、2000 年 1 月 1 日 3 時」生成します。  
  
-   **DTS\_SHORTDATEFORMAT**は短い形式の日付を表示し、「1\/3\/00 "のような出力が生成されます。  
  
-   **DTS\_TIMEFORMAT**は長い形式の時刻を表示し、「5:31 "などの出力を生成する: 42 PM」。  
  
 ただし、カスタム書式指定文字列を使用して日付または時刻の外観をカスタマイズできます。  このカスタム文字列は、両方の既存の書式指定文字 nonformat、の文字、または組み合わせで構成されています。  カスタム文字列をビルドした場合は、カスタム文字列に渡す [CDateTimeCtrl::SetFormat](../Topic/CDateTimeCtrl::SetFormat.md) に呼び出しを行ってください。  日時指定のコントロールでは、カスタム書式指定文字列を使用して現在の値を表示します。  
  
 次のコード例は、`m_dtPicker` が `CDateTimeCtrl` オブジェクト\) 1 個の解決策を示します:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/CPP/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]  
  
 カスタム書式指定文字列のほかに、日時指定のコントロールは、[コールバック フィールド](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)をサポートします。  
  
## 参照  
 [CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)   
 [コントロール](../mfc/controls-mfc.md)