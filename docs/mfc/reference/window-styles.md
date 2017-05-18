---
title: "ウィンドウ スタイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WS_MINIMIZEBOX
- WS_SIZEBOX
- WS_CLIPCHILDREN
- WS_TILED
- WS_GROUP
- WS_VSCROLL
- WS_CHILD
- WS_TABSTOP
- WS_HSCROLL
- WS_THICKFRAME
- WS_DISABLED
- WS_POPUP
- WS_ICONIC
- WS_MAXIMIZE
- WS_VISIBLE
- WS_POPUPWINDOW
- WS_TILEDWINDOW
- WS_DLGFRAME
- WS_MINIMIZE
- WS_CAPTION
- WS_OVERLAPPED
- WS_BORDER
- WS_MAXIMIZEBOX
- WS_OVERLAPPEDWINDOW
- WS_SYSMENU
- WS_CHILDWINDOW
- WS_CLIPSIBLINGS
dev_langs:
- C++
helpviewer_keywords:
- WS_THICKFRAME constant
- WS_TILEDWINDOW constant
- WS_MAXIMIZEBOX constant
- WS_DLGFRAME constant
- WS_CHILDWINDOW constant
- window styles, in MFC
- WS_CHILD constant
- WS_GROUP constant
- WS_MINIMIZE constant
- WS_CAPTION constant
- WS_MAXIMIZE constant
- WS_POPUP constant
- WS_SYSMENU constant
- WS_TILED constant
- window styles
- WS_POPUPWINDOW constant
- WS_CLIPSIBLINGS constant
- WS_BORDER constant
- WS_DISABLED constant
- WS_VSCROLL constant
- WS_OVERLAPPED constant
- WS_MINIMIZEBOX constant
- WS_VISIBLE constant
- WS_OVERLAPPEDWINDOW constant
- WS_TABSTOP constant
- WS_ICONIC constant
- WS_SIZEBOX constant
- WS_HSCROLL constant
- WS_CLIPCHILDREN constant
- styles, windows
ms.assetid: c85ffbe4-f4ff-4227-917a-48ec4a411842
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: d814e3a10132fb3fe88969ce434f8286b02afba5
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="window-styles"></a>ウィンドウ スタイル
-   `WS_BORDER`罫線のあるウィンドウを作成します。  
  
-   **WS_CAPTION**タイトル バーを持つウィンドウを作成 (意味、`WS_BORDER`スタイル)。 は使用できません、 **WS_DLGFRAME**スタイル。  
  
-   **WS_CHILD**子ウィンドウを作成します。 `WS_POPUP` スタイルと一緒に使うことはできません。  
  
-   **WS_CHILDWINDOW**と同じ、 **WS_CHILD**スタイル。  
  
-   **WS_CLIPCHILDREN**親ウィンドウ内に描画するときに、子ウィンドウにより占有されている領域を除外します。 親ウィンドウを作成するときに使用します。  
  
-   **WS_CLIPSIBLINGS**相互に比較したクリップ子ウィンドウです。 つまり、特定の子ウィンドウが描画メッセージを受信すると、 **WS_CLIPSIBLINGS**スタイルは、他のすべての重複した子ウィンドウを更新する子ウィンドウの領域の外をクリップします。 (場合**WS_CLIPSIBLINGS**は付与しませんし、子ウィンドウが重なる、子ウィンドウのクライアント領域内に描画するときに、隣接する子ウィンドウのクライアント領域内に描画することができます)。使用するため、 **WS_CHILD**のみのスタイルを設定します。  
  
-   **WS_DISABLED**最初に無効になっているウィンドウを作成します。  
  
-   **WS_DLGFRAME**タイトルのない二重境界線を持つウィンドウを作成します。  
  
-   **WS_GROUP**をユーザーに移動できるコントロール&1; つのコントロールから次の矢印キーでのグループの最初のコントロールを指定します。 定義されたすべてのコントロール、 **WS_GROUP**スタイル**FALSE**後の最初のコントロールが同じグループに属しています。 次のコントロールで、 **WS_GROUP**スタイルは、次のグループ (つまり、1 つのグループの最後、次の開始位置) を起動します。  
  
-   **WS_HSCROLL**水平スクロール バーを持つウィンドウを作成します。  
  
-   **WS_ICONIC**最初に最小化ウィンドウを作成します。 同じ、 **WS_MINIMIZE**スタイル。  
  
-   **WS_MAXIMIZE**最大サイズのウィンドウを作成します。  
  
-   **WS_MAXIMIZEBOX**を最大化ボタンを持つウィンドウを作成します。  
  
-   **WS_MINIMIZE**最初に最小化ウィンドウを作成します。 使用するため、 **WS_OVERLAPPED**のみのスタイルを設定します。  
  
-   **WS_MINIMIZEBOX**を最小化ボタンを持つウィンドウを作成します。  
  
-   **WS_OVERLAPPED**オーバー ラップ ウィンドウを作成します。 オーバーラップ ウィンドウには、通常キャプションと境界線があります。  
  
-   **WS_OVERLAPPEDWINDOW**オーバー ラップ ウィンドウを作成、 **WS_OVERLAPPED**、 **WS_CAPTION**、 **WS_SYSMENU**、 **WS_THICKFRAME**、 **WS_MINIMIZEBOX**、および**WS_MAXIMIZEBOX**スタイル。  
  
-   `WS_POPUP`ポップアップ ウィンドウを作成します。 は使用できません、 **WS_CHILD**スタイル。  
  
-   **WS_POPUPWINDOW**ポップアップ ウィンドウを作成、 `WS_BORDER`、 `WS_POPUP`、および**WS_SYSMENU**スタイル。 **WS_CAPTION**とスタイルを組み合わせることは、 **WS_POPUPWINDOW**スタイルをコントロールのメニューが表示されるようにします。  
  
-   **WS_SIZEBOX**ウィンドウ サイズ変更境界を作成します。 同じ、 **WS_THICKFRAME**スタイル。  
  
-   **WS_SYSMENU**のタイトル バーにコントロール メニュー ボックスのあるウィンドウを作成します。 タイトル バーのあるウィンドウで使用します。  
  
-   **WS_TABSTOP**ユーザーが TAB キーを使用して移動できるコントロールの任意の数のいずれかを指定します。 TAB キーで指定された次のコントロールにユーザーの移動、 **WS_TABSTOP**スタイル。  
  
-   **WS_THICKFRAME**ウィンドウ フレームのウィンドウのサイズを使用できるを作成します。  
  
-   **WS_TILED**オーバー ラップ ウィンドウを作成します。 オーバーラップ ウィンドウには、タイトル バーと境界線があります。 同じ、 **WS_OVERLAPPED**スタイル。  
  
-   **WS_TILEDWINDOW**オーバー ラップ ウィンドウを作成、 **WS_OVERLAPPED**、 **WS_CAPTION**、 **WS_SYSMENU**、 **WS_THICKFRAME**、 **WS_MINIMIZEBOX**、および**WS_MAXIMIZEBOX**スタイル。 同じ、 **WS_OVERLAPPEDWINDOW**スタイル。  
  
-   **WS_VISIBLE**が最初に表示されるウィンドウを作成します。  
  
-   **WS_VSCROLL**垂直スクロール バーを持つウィンドウを作成します。  
  
## <a name="see-also"></a>関連項目  
 [MFC で使用するスタイル](../../mfc/reference/styles-used-by-mfc.md)   
 [Cwnd::create](../../mfc/reference/cwnd-class.md#create)   
 [とき](../../mfc/reference/cwnd-class.md#createex)   
 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)


