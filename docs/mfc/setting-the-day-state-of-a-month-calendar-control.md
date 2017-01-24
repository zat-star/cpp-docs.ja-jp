---
title: "月間予定表コントロールの日付状態の設定 | Microsoft Docs"
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
  - "MCN_GETDAYSTATE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMonthCalCtrl クラス, 設定 (日付状態の情報を)"
  - "MCN_GETDAYSTATE 通知"
  - "月間予定表コントロール, 日付状態の情報"
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 月間予定表コントロールの日付状態の設定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

月間予定表コントロール属性の 1 つが月の日付のコントロールの日の状態と呼ばれる情報を格納する機能です。  この情報が現在表示されている月の特定の日付を選択するために使用されます。  
  
> [!NOTE]
>  `CMonthCalCtrl` オブジェクトは日付の状態情報を表示する **MCS\_DAYSTATE** のスタイルが必要です。  
  
 日の状態情報が 32 ビット データ型、**MONTHDAYSTATE**として表現されます。  **MONTHDAYSTATE** ビット フィールド \(1 ~ 31\) の各ビットは、か月の日の状態を表します。  ほとんどの場合、対応する日は太字で表示されます。; それ以外の場合は、文字なしで表示されます。  
  
 月間予定表コントロールの日の状態を設定するための 2 種類のメソッドがあります。: 明示的に [CMonthCalCtrl::SetDayState](../Topic/CMonthCalCtrl::SetDayState.md) へまたは **MCN\_GETDAYSTATE** 通知メッセージの処理による呼び出しです。  
  
## MCN\_GETDAYSTATE 通知メッセージの処理  
 **MCN\_GETDAYSTATE** メッセージがコントロールによって表示されている月の日付がどのように表示されるかを判断するために送信されます。  
  
> [!NOTE]
>  コントロールが以前とキャッシュする新しい月が選択されるたびに従う月、表示月に関して、この通知を受け取ります。  
  
 適切にこのメッセージを処理する場合、初期化し適切な値を **MONTHDAYSTATE** 構造体の配列を初期化します、新しい情報で関連の構造体メンバーを一つの月日の状態情報が中要求されているかを確認する必要があります。  必要な手順を説明する次の手順は **MONTHDAYSTATE** オブジェクトの `m_monthcal` と配列という `CMonthCalCtrl` オブジェクトがある `mdState`と見なされます。  
  
#### MCN\_GETDAYSTATE の通知メッセージを処理するには  
  
1.  プロパティ ウィンドウを使用して、`m_monthcal` オブジェクトに **MCN\_GETDAYSTATE** 通知メッセージのハンドラーを追加します。[関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)を参照してください。  
  
2.  ハンドラーの本体に、次のコードを追加する:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/CPP/setting-the-day-state-of-a-month-calendar-control_1.cpp)]  
  
     この例では、適切な型に `pNMHDR` のポインターを変換し、情報を一つの月が要求されているかを判断します。`pDayState->cDayState`\)。  各月の場合、現在の`pDayState->prgDayState[i]`bitfield \(\) はゼロに初期化され、次に必要な日付 \(この場合は各月の第 15\) に設定されます。  
  
## 参照  
 [CMonthCalCtrl の使い方](../Topic/Using%20CMonthCalCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)