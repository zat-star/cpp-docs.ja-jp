---
title: "CMonthCalCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMonthCalCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMonthCalCtrl クラス"
  - "コモン コントロール, Internet Explorer 4.0"
  - "Internet Explorer 4.0 コモン コントロール"
  - "月間予定表コントロール"
  - "月間予定表コントロール, CMonthCalCtrl クラス"
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMonthCalCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

月間予定表コントロールの機能がカプセル化されています。  
  
## 構文  
  
```  
class CMonthCalCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMonthCalCtrl::CMonthCalCtrl](../Topic/CMonthCalCtrl::CMonthCalCtrl.md)|`CMonthCalCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMonthCalCtrl::Create](../Topic/CMonthCalCtrl::Create.md)|月間予定表コントロールを作成し、`CMonthCalCtrl` のオブジェクトにアタッチします。|  
|[CMonthCalCtrl::GetCalendarBorder](../Topic/CMonthCalCtrl::GetCalendarBorder.md)|現在の月間予定表コントロールの境界線の幅を取得します。|  
|[CMonthCalCtrl::GetCalendarCount](../Topic/CMonthCalCtrl::GetCalendarCount.md)|現在の月間予定表コントロールに表示される暦の数を取得します。|  
|[CMonthCalCtrl::GetCalendarGridInfo](../Topic/CMonthCalCtrl::GetCalendarGridInfo.md)|現在の月間予定表コントロールについての情報を取得します。|  
|[CMonthCalCtrl::GetCalID](../Topic/CMonthCalCtrl::GetCalID.md)|現在の月間予定表コントロールのカレンダーの識別子を取得します。|  
|[CMonthCalCtrl::GetColor](../Topic/CMonthCalCtrl::GetColor.md)|月間予定表コントロールの指定した領域の色を取得します。|  
|[CMonthCalCtrl::GetCurrentView](../Topic/CMonthCalCtrl::GetCurrentView.md)|現在の月間カレンダー コントロールで現在表示されているビューを取得します。|  
|[CMonthCalCtrl::GetCurSel](../Topic/CMonthCalCtrl::GetCurSel.md)|現在選択されている日付までに示すようにシステム時刻を取得します。|  
|[CMonthCalCtrl::GetFirstDayOfWeek](../Topic/CMonthCalCtrl::GetFirstDayOfWeek.md)|最初の日をカレンダーの左端の列に表示されるように取得します。|  
|[CMonthCalCtrl::GetMaxSelCount](../Topic/CMonthCalCtrl::GetMaxSelCount.md)|月間予定表コントロールで選択できる日付の現在の最大数を取得します。|  
|[CMonthCalCtrl::GetMaxTodayWidth](../Topic/CMonthCalCtrl::GetMaxTodayWidth.md)|の最大幅を「今日」文字列を結びつける現在の月間予定表コントロールに対して取得します。|  
|[CMonthCalCtrl::GetMinReqRect](../Topic/CMonthCalCtrl::GetMinReqRect.md)|月間予定表コントロールでいる月を表示するために必要な最小サイズを取得します。|  
|[CMonthCalCtrl::GetMonthDelta](../Topic/CMonthCalCtrl::GetMonthDelta.md)|月間予定表コントロールのスクロール速度を取得します。|  
|[CMonthCalCtrl::GetMonthRange](../Topic/CMonthCalCtrl::GetMonthRange.md)|取得し、月間予定表コントロールの表示の最大値と下限を表す情報に日付を入力します。|  
|[CMonthCalCtrl::GetRange](../Topic/CMonthCalCtrl::GetRange.md)|現在の最小を取得し、最大値は月間予定表コントロールのセットに日付を入力します。|  
|[CMonthCalCtrl::GetSelRange](../Topic/CMonthCalCtrl::GetSelRange.md)|取得し、上限を表す情報に日付と日付の下限はユーザーによって現在選択されている範囲。|  
|[CMonthCalCtrl::GetToday](../Topic/CMonthCalCtrl::GetToday.md)|月間予定表コントロールに対して「今日として」指定された日付の日付情報を取得します。|  
|[CMonthCalCtrl::HitTest](../Topic/CMonthCalCtrl::HitTest.md)|月間予定表コントロールのセクションが画面上の特定の位置によって決まります。|  
|[CMonthCalCtrl::IsCenturyView](../Topic/CMonthCalCtrl::IsCenturyView.md)|現在の月間予定表コントロールの現在のビューが世紀のビューであるかどうかを示します。|  
|[CMonthCalCtrl::IsDecadeView](../Topic/CMonthCalCtrl::IsDecadeView.md)|現在の月間予定表コントロールの現在のビューが十年のビューであるかどうかを示します。|  
|[CMonthCalCtrl::IsMonthView](../Topic/CMonthCalCtrl::IsMonthView.md)|現在の月間予定表コントロールの現在のビューが表示月のビューであるかどうかを示します。|  
|[CMonthCalCtrl::IsYearView](../Topic/CMonthCalCtrl::IsYearView.md)|現在の月間予定表コントロールの現在のビューが年のビューであるかどうかを示します。|  
|[CMonthCalCtrl::SetCalendarBorder](../Topic/CMonthCalCtrl::SetCalendarBorder.md)|現在の月間予定表コントロールの境界線の幅を設定します。|  
|[CMonthCalCtrl::SetCalendarBorderDefault](../Topic/CMonthCalCtrl::SetCalendarBorderDefault.md)|現在の月間予定表コントロールの境界線の既定の幅を設定します。|  
|[CMonthCalCtrl::SetCalID](../Topic/CMonthCalCtrl::SetCalID.md)|現在の月間予定表コントロールのカレンダーの識別子を設定します。|  
|[CMonthCalCtrl::SetCenturyView](../Topic/CMonthCalCtrl::SetCenturyView.md)|現在の月間予定表コントロールが世紀のビューが表示されるように設定します。|  
|[CMonthCalCtrl::SetColor](../Topic/CMonthCalCtrl::SetColor.md)|月間予定表コントロールの指定した領域の色を設定します。|  
|[CMonthCalCtrl::SetCurrentView](../Topic/CMonthCalCtrl::SetCurrentView.md)|現在の月間予定表コントロールを指定したビューが表示されるように設定します。|  
|[CMonthCalCtrl::SetCurSel](../Topic/CMonthCalCtrl::SetCurSel.md)|月間予定表コントロールに対して現在選択されている日付を設定します。|  
|[CMonthCalCtrl::SetDayState](../Topic/CMonthCalCtrl::SetDayState.md)|月間予定表コントロールの日の表示を設定します。|  
|[CMonthCalCtrl::SetDecadeView](../Topic/CMonthCalCtrl::SetDecadeView.md)|モードをビューに現在の月間予定表コントロールを設定します。|  
|[CMonthCalCtrl::SetFirstDayOfWeek](../Topic/CMonthCalCtrl::SetFirstDayOfWeek.md)|カレンダーの左端の列に表示する週間の日付を設定します。|  
|[CMonthCalCtrl::SetMaxSelCount](../Topic/CMonthCalCtrl::SetMaxSelCount.md)|月間予定表コントロールで選択できる日付の最大数を設定します。|  
|[CMonthCalCtrl::SetMonthDelta](../Topic/CMonthCalCtrl::SetMonthDelta.md)|月間予定表コントロールのスクロール速度を設定します。|  
|[CMonthCalCtrl::SetMonthView](../Topic/CMonthCalCtrl::SetMonthView.md)|現在の月間予定表コントロールを月のビューが表示されるように設定します。|  
|[CMonthCalCtrl::SetRange](../Topic/CMonthCalCtrl::SetRange.md)|最小値を設定し、許可される最大値は、月間カレンダー コントロールで日付を入力します。|  
|[CMonthCalCtrl::SetSelRange](../Topic/CMonthCalCtrl::SetSelRange.md)|特定の日付範囲に月間予定表コントロールのオプションを設定します。|  
|[CMonthCalCtrl::SetToday](../Topic/CMonthCalCtrl::SetToday.md)|現在の曜日のカレンダー コントロールを設定します。|  
|[CMonthCalCtrl::SetYearView](../Topic/CMonthCalCtrl::SetYearView.md)|年のビューに現在の月間予定表コントロールを設定します。|  
|[CMonthCalCtrl::SizeMinReq](../Topic/CMonthCalCtrl::SizeMinReq.md)|少なくとも一方、1 年 1 月のサイズに月間予定表コントロールを再描画します。|  
|[CMonthCalCtrl::SizeRectToMin](../Topic/CMonthCalCtrl::SizeRectToMin.md)|現在の月間予定表コントロールに対して、指定された四角形ですべての暦をに適合含めることができる最小の四角形を計算します。|  
  
## 解説  
 月間カレンダー コントロールは、ユーザーが日付を選択できる簡単な暦のインターフェイスを提供します。  ユーザーは、表示は、次の方法で変更できます:  
  
-   前後にスクロールすると、転送、月単位で。  
  
-   \( **MCS\_NOTODAY** のスタイルが使用されていない場合\)、今日のテキストの現在の曜日を表示するには、をクリックします。  
  
-   ポップアップ メニューから月または年のオプション。  
  
 オブジェクトにさまざまなスタイルを適用して、月間カレンダー コントロールを作成するときにカスタマイズできます。  これらのスタイルは [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [月間予定表コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760919) で説明します。  
  
 月間カレンダー コントロールは 1 か月以上を太字表示を表示して、特殊な日 \(休日など\) を示すことができます。日付  
  
 月間予定表コントロールの使用の詳細については、[を使用して CMonthCalCtrl](../Topic/Using%20CMonthCalCtrl.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CMonthCalCtrl`  
  
## 必要条件  
 **Header:** afxdtctl.h  
  
## 参照  
 [MFC CMNCTRL1 サンプル](../../top/visual-cpp-samples.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDateTimeCtrl クラス](../../mfc/reference/cdatetimectrl-class.md)