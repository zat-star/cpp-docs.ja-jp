---
title: "MFC で使用するスタイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.styles
dev_langs:
- C++
helpviewer_keywords:
- edit styles [MFC]
- window styles, in MFC
- styles
- frame windows, styles
- message-box styles
- styles, MFC
- buttons, MFC toolbars
- list boxes, styles
- static styles
- scroll-bar styles [MFC]
- combo boxes, styles
- extended window styles
ms.assetid: d3b9af37-31b5-4c97-a8ad-189fd724b04c
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 344d2ce3de15403e17f29dc9504253cbb0ade607
ms.lasthandoff: 02/24/2017

---
# <a name="styles-used-by-mfc"></a>MFC で使用するスタイル
対応する MFC オブジェクトを作成する場合は、次のスタイルを使用します。 ほとんどの場合、これらのスタイルを設定、`dwStyle`クラスのパラメーター**作成**関数です。  
  
### <a name="mfc-styles"></a>MFC のスタイル  
  
|スタイル|説明|  
|-----------|-----------------|  
|[ボタン スタイル](../../mfc/reference/button-styles.md)|適用対象[CButton クラス](../../mfc/reference/cbutton-class.md)ラジオ ボタンなどのオブジェクトのチェック ボックス、プッシュ ボタン。 内のスタイルの組み合わせを指定、`dwStyle`のパラメーター [CButton::Create](../../mfc/reference/cbutton-class.md#create)します。|  
|[コンボ ボックス スタイル](../../mfc/reference/combo-box-styles.md)|適用対象[CComboBox クラス](../../mfc/reference/ccombobox-class.md)オブジェクトです。 内のスタイルの組み合わせを指定、`dwStyle`のパラメーター [CComboBox::Create](../../mfc/reference/ccombobox-class.md#create)します。|  
|[エディット スタイル](../../mfc/reference/edit-styles.md)|適用対象[CEdit クラス](../../mfc/reference/cedit-class.md)のオブジェクト。 内のスタイルの組み合わせを指定、`dwStyle`のパラメーター [CEdit::Create](../../mfc/reference/cedit-class.md#create)します。|  
|[フレーム ウィンドウ スタイル](../../mfc/reference/frame-window-styles-mfc.md)|適用対象[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)オブジェクトです。 内のスタイルの組み合わせを指定、`dwStyle`のパラメーター [CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)します。|  
|[リスト ボックス スタイル](../../mfc/reference/list-box-styles.md)|適用対象[CListBox クラス](../../mfc/reference/clistbox-class.md)オブジェクトです。 内のスタイルの組み合わせを指定、`dwStyle`のパラメーター [CListBox::Create](../../mfc/reference/clistbox-class.md#create)します。|  
|[メッセージ ボックス スタイル](../../mfc/reference/message-box-styles.md)|適用対象[AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox)項目。 内のスタイルの組み合わせを指定、`nType`のパラメーター`AfxMessageBox`します。|  
|[スクロール バー スタイル](../../mfc/reference/scroll-bar-styles.md)|適用対象[CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)オブジェクトです。 内のスタイルの組み合わせを指定、`dwStyle`のパラメーター [CScrollBar::Create](../../mfc/reference/cscrollbar-class.md#create)します。|  
|[静的コントロール スタイル](../../mfc/reference/static-styles.md)|適用対象[CStatic クラス](../../mfc/reference/cstatic-class.md)オブジェクトです。 内のスタイルの組み合わせを指定、`dwStyle`のパラメーター [CStatic::Create](../../mfc/reference/cstatic-class.md#create)します。|  
|[ウィンドウ スタイル](../../mfc/reference/window-styles.md)|適用対象[CWnd クラス](../../mfc/reference/cwnd-class.md)オブジェクトです。 内のスタイルの組み合わせを指定、`dwStyle`のパラメーター [cwnd::create](../../mfc/reference/cwnd-class.md#create)または[とき](../../mfc/reference/cwnd-class.md#createex)します。|  
|[拡張ウィンドウ スタイル](../../mfc/reference/extended-window-styles.md)|適用対象[CWnd クラス](../../mfc/reference/cwnd-class.md)オブジェクトです。 内のスタイルの組み合わせを指定、`dwExStyle`のパラメーター[とき](../../mfc/reference/cwnd-class.md#createex)します。|  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../mfc/class-library-overview.md)


