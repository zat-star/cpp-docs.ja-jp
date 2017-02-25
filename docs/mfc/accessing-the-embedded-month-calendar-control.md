---
title: "埋め込み月間予定表コントロールへのアクセス | Microsoft Docs"
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
  - "CDateTimeCtrl クラス, アクセス (埋め込まれたコントロールに)"
  - "CMonthCalCtrl クラス, 変更 (フォントを)"
  - "DateTimePicker コントロール [MFC]"
  - "DateTimePicker コントロール [MFC], アクセス (月間予定表に)"
  - "月間予定表コントロール, 変更 (フォントを)"
  - "月間予定表コントロール, 埋め込み (日時指定の)"
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 埋め込み月間予定表コントロールへのアクセス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

埋め込まれたな月間予定表コントロール オブジェクトは、呼び出しで `CDateTimeCtrl` オブジェクトから [GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md) のメンバー関数にアクセスできます。  
  
> [!NOTE]
>  埋め込まれたな月間予定表コントロールは日時指定のコントロールに設定されている **DTS\_UPDOWN** のスタイルがない場合にのみ使用されます。  
  
 これは埋め込みコントロールが表示される前に、特定の属性を変更する場合に便利です。  これを行うには、**DTN\_DROPDOWN** 通知を取得し、月間予定表コントロール \([CDateTimeCtrl::GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md)を使用\) と変更を処理してください。  ただし、月間予定表コントロールは永続的ではありません。  
  
 つまり、ユーザーが月間予定表コントロールの表示、新しい月間予定表コントロール作成されます \(**DTN\_DROPDOWN** 通知の前に\)。  コントロール \(**DTN\_CLOSEUP** 通知\) の後にユーザーが終了すると、破棄されます。  これは埋め込みコントロールが終了すると埋め込みコントロールが表示される前に、変更する属性が失われることを意味します。  
  
 次の例では **DTN\_DROPDOWN** 通知のハンドラーを使用して、この手順を示します。  コードは灰色に [SetMonthCalColor](../Topic/CDateTimeCtrl::SetMonthCalColor.md)を呼び出して月間予定表コントロールの背景色を選択し、変更します。  コードは次のとおりです。:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/CPP/accessing-the-embedded-month-calendar-control_1.cpp)]  
  
 前に説明したように、月間予定表コントロールのプロパティへのすべての変更は、2 種類の例外に埋め込まれたコントロールが終了すると、失われます。  最初の例外、月間予定表コントロールの色は、既に参照されています。  2 番目の例外は月間予定表コントロールに使用しているフォントです。  既存のフォントのハンドルを渡す [CDateTimeCtrl::SetMonthCalFont](../Topic/CDateTimeCtrl::SetMonthCalFont.md)を呼び出すことによって、既定のフォントを変更できます。  次の例では、\(`m_dtPicker` の日時コントロール オブジェクト\) は、1 とおりのメソッドを示しています。:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/CPP/accessing-the-embedded-month-calendar-control_2.cpp)]  
  
 月間予定表が表示されるときにフォントが `CDateTimeCtrl::SetMonthCalFont`と、新しいフォント格納および使用される変更された場合。  
  
## 参照  
 [CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)   
 [コントロール](../mfc/controls-mfc.md)