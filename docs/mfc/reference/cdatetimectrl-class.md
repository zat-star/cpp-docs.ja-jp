---
title: "CDateTimeCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDateTimeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDateTimeCtrl クラス"
  - "日付選択機能"
  - "DateTimePicker コントロール [MFC]"
  - "DateTimePicker コントロール [MFC], CDateTimeCtrl クラス"
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
caps.latest.revision: 23
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDateTimeCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

日時指定コントロールの機能がカプセル化されています。  
  
## 構文  
  
```  
class CDateTimeCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDateTimeCtrl::CDateTimeCtrl](../Topic/CDateTimeCtrl::CDateTimeCtrl.md)|`CDateTimeCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDateTimeCtrl::CloseMonthCal](../Topic/CDateTimeCtrl::CloseMonthCal.md)|現在の日付と時刻の指定コントロールを閉じます。|  
|[CDateTimeCtrl::Create](../Topic/CDateTimeCtrl::Create.md)|日時指定コントロールを作成し、`CDateTimeCtrl` のオブジェクトにアタッチします。|  
|[CDateTimeCtrl::GetDateTimePickerInfo](../Topic/CDateTimeCtrl::GetDateTimePickerInfo.md)|現在の日付と時刻の指定コントロールについての情報を取得します。|  
|[CDateTimeCtrl::GetIdealSize](../Topic/CDateTimeCtrl::GetIdealSize.md)|現在の日付または時刻を表示するために必要な日時指定コントロールの適切なサイズを返します。|  
|[CDateTimeCtrl::GetMonthCalColor](../Topic/CDateTimeCtrl::GetMonthCalColor.md)|日時指定コントロール内で月間カレンダーの特定の部分の色を取得します。|  
|[CDateTimeCtrl::GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md)|日時指定コントロールに関連付けられている `CMonthCalCtrl` のオブジェクトを取得します。|  
|[CDateTimeCtrl::GetMonthCalFont](../Topic/CDateTimeCtrl::GetMonthCalFont.md)|現在の日時指定コントロールの子月間カレンダー コントロールで使用するフォントを取得します。|  
|[CDateTimeCtrl::GetMonthCalStyle](../Topic/CDateTimeCtrl::GetMonthCalStyle.md)|現在の日付と時刻の指定コントロールのスタイルを取得します。|  
|[CDateTimeCtrl::GetRange](../Topic/CDateTimeCtrl::GetRange.md)|日時指定コントロールの現在の最小値と最大値によって認められるシステム時刻を取得します。|  
|[CDateTimeCtrl::GetTime](../Topic/CDateTimeCtrl::GetTime.md)|現在選択されている時刻を日時指定コントロールから取得し、`SYSTEMTIME` の指定された構造体に格納します。|  
|[CDateTimeCtrl::SetFormat](../Topic/CDateTimeCtrl::SetFormat.md)|指定された書式の文字列に従って日時指定コントロールの表示を設定します。|  
|[CDateTimeCtrl::SetMonthCalColor](../Topic/CDateTimeCtrl::SetMonthCalColor.md)|日時指定コントロール内で月間カレンダーの特定の部分の色を設定します。|  
|[CDateTimeCtrl::SetMonthCalFont](../Topic/CDateTimeCtrl::SetMonthCalFont.md)|日時指定コントロールの子月間予定表コントロールが使用するフォントを設定します。|  
|[CDateTimeCtrl::SetMonthCalStyle](../Topic/CDateTimeCtrl::SetMonthCalStyle.md)|現在の日付と時刻の指定コントロールのスタイルを設定します。|  
|[CDateTimeCtrl::SetRange](../Topic/CDateTimeCtrl::SetRange.md)|日時指定コントロールの最小値と最大値によって認められるシステム時刻を設定します。|  
|[CDateTimeCtrl::SetTime](../Topic/CDateTimeCtrl::SetTime.md)|日時指定コントロールのタイムアウトを設定します。|  
  
## 解説  
 日時指定コントロール \(コントロール\) は DTP のユーザーと時刻の情報を交換するための簡単なインターフェイスを提供します。  このインターフェイスは、それぞれがコントロールに格納された日付と時刻の情報の一部を表示するフィールドが含まれています。  ユーザーは、特定のフィールド文字列の内容を変更してコントロールに格納されている情報を変更できます。  ユーザーがマウスまたはキーボードを使用してフィールドからフィールドに移動できます。  
  
 オブジェクトにさまざまなスタイルを適用して、日時指定コントロールを作成するときにカスタマイズできます。  日時指定コントロールに固有のスタイルの詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] の [日時指定、スタイルを制御します](http://msdn.microsoft.com/library/windows/desktop/bb761728) を参照してください。  書式スタイルを使用して DTP のコントロールの表示形式を設定できます。  これらの書式スタイルは [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] のトピック [日時指定、スタイルを制御します](http://msdn.microsoft.com/library/windows/desktop/bb761728)「形式の下にスタイルで」説明します。  
  
 日時指定コントロールは、[を使用して CDateTimeCtrl](../../mfc/using-cdatetimectrl.md)に記述されているコールバックと通知を使用します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CDateTimeCtrl`  
  
## 必要条件  
 **Header:** afxdtctl.h  
  
## 参照  
 [MFC CMNCTRL1 サンプル](../../top/visual-cpp-samples.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl クラス](../../mfc/reference/cmonthcalctrl-class.md)