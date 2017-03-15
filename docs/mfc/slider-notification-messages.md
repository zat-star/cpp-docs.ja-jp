---
title: "スライダー コントロールの通知メッセージ | Microsoft Docs"
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
  - "CSliderCtrl クラス, 通知"
  - "メッセージ, 通知"
  - "通知, CSliderCtrl"
  - "スライダー コントロール, 通知メッセージ"
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# スライダー コントロールの通知メッセージ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

スライダー コントロールでスライダー コントロールの方向に応じて、親 `WM_HSCROLL` または `WM_VSCROLL` メッセージを送信することによってユーザー アクションの親ウィンドウに通知します。  これらのメッセージを処理するには、親ウィンドウへ `WM_HSCROLL` と `WM_VSCROLL` メッセージのハンドラーを追加します。  [OnHScroll](../Topic/CWnd::OnHScroll.md) と [OnVScroll](../Topic/CWnd::OnVScroll.md) のメンバー関数は [CSliderCtrl](../mfc/reference/csliderctrl-class.md) オブジェクトは、スライダーの通知コード、位置、およびポインターに渡されます。  `CSliderCtrl` オブジェクトを指すポインターの型が **CScrollBar \*** であることに注意してください。  スライダー コントロールを処理する必要がある場合は、このポインターを型キャストが必要になる場合があります。  
  
 スクロール バーの通知コードを使用するのではなく、スライダー コントロールは通知コードのセットを送信します。  スライダー コントロールは、ユーザーがスライダー コントロールでキーボードを使用してやり取りする場合にのみ **TB\_BOTTOM**、**TB\_LINEDOWN**、**TB\_LINEUP**と **TB\_TOP** 通知コードを送信します。  **TB\_THUMBPOSITION** と **TB\_THUMBTRACK** 通知メッセージは、マウスを使用しているときにだけ送られます。  **TB\_ENDTRACK**、**TB\_PAGEDOWN**と **TB\_PAGEUP** 通知コードはどちらの場合も、送信されます。  
  
 次の表では、スライダー コントロールの通知メッセージとイベント \(仮想キー コードまたはマウス イベント\)、これに送信される通知の一覧です。\(標準の仮想キー コードの一覧については、" Winuser.h を参照してください\)。  
  
|通知メッセージ|イベント通知を送信します。|  
|-------------|-------------------|  
|**TB\_BOTTOM**|**VK\_END**|  
|**TB\_ENDTRACK**|`WM_KEYUP` \(ユーザーは対応する仮想キー コードを送信するキーを離したとき\)|  
|**TB\_LINEDOWN**|**VK\_RIGHT** または **VK\_DOWN**|  
|**TB\_LINEUP**|**VK\_LEFT** または **VK\_UP**|  
|**TB\_PAGEDOWN**|**VK\_NEXT** \(ユーザーはスライダー上または下の右側にチャネルをクリックする\)|  
|**TB\_PAGEUP**|**VK\_PRIOR** \(ユーザーはスライダー上または左側のチャネルをクリックする\)|  
|**TB\_THUMBPOSITION**|**TB\_THUMBTRACK** 通知メッセージの後`WM_LBUTTONUP`|  
|**TB\_THUMBTRACK**|スライダーを動かして \(ユーザーはスライダーをドラッグ\)|  
|**TB\_TOP**|**VK\_HOME**|  
  
## 参照  
 [CSliderCtrl の使い方](../mfc/using-csliderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)