---
title: "拡張ウィンドウ スタイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WS_EX_TOOLWINDOW
- WS_EX_LEFTSCROLLBAR
- WS_EX_RTLREADING
- WS_EX_WINDOWEDGE
- WS_EX_CLIENTEDGE
- WS_EX_STATICEDGE
- WS_EX_LTRREADING
- WS_EX_DLGMODALFRAME
- WS_EX_RIGHTSCROLLBAR
- WS_EX_CONTROLPARENT
- WS_EX_ACCEPTFILES
- WS_EX_TRANSPARENT
- WS_EX_RIGHT
- WS_EX_APPWINDOW
- WS_EX_TOPMOST
- WS_EX_CONTEXTHELP
- WS_EX_MDICHILD
- WS_EX_LEFT
- WS_EX_OVERLAPPEDWINDOW
- WS_EX_PALETTEWINDOW
- WS_EX_NOPARENTNOTIFY
dev_langs:
- C++
helpviewer_keywords:
- WS_EX_PALETTEWINDOW constant
- WS_EX_NOPARENTNOTIFY constant
- WS_EX_RIGHT constant
- WS_EX_DLGMODALFRAME constant
- WS_EX_APPWINDOW constant
- WS_EX_STATICEDGE constant
- WS_EX_LTRREADING constant
- WS_EX_RIGHTSCROLLBAR constant
- WS_EX_CONTROLPARENT constant
- WS_EX_MDICHILD constant
- WS_EX_TOPMOST constant
- WS_EX_RTLREADING constant
- WS_EX_LEFT constant
- WS_EX_TOOLWINDOW constant
- WS_EX_ACCEPTFILES constant
- WS_EX_WINDOWEDGE constant
- WS_EX_OVERLAPPEDWINDOW constant
- extended window styles
- WS_EX_LEFTSCROLLBAR constant
- WS_EX_TRANSPARENT constant
- WS_EX_CLIENTEDGE constant
- WS_EX_CONTEXTHELP constant
- styles, windows
ms.assetid: d18e6c69-0a01-49ed-b58a-55b3802b47c1
caps.latest.revision: 14
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
ms.openlocfilehash: e5a735ffcdaa78a4764e57b3c311979f24b7fdda
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="extended-window-styles"></a>拡張ウィンドウ スタイル
-   **WS_EX_ACCEPTFILES**このスタイルで作成したウィンドウがドラッグ アンド ドロップ ファイルを受け入れることを指定します。  
  
-   **WS_EX_APPWINDOW**ウィンドウが表示される、タスク バー上にトップレベル ウィンドウを強制します。  
  
-   **WS_EX_CLIENTEDGE**ウィンドウの外観を 3D 表示を指定します-つまり、くぼみ線で、縁取りします。  
  
-   **WS_EX_CONTEXTHELP**ウィンドウのタイトル バーに疑問符 () が含まれています。 ユーザーがこの疑問符をクリックすると、カーソルは、疑問符付きのポインターに変化します。 子を受け取る場合は、子ウィンドウ をクリックして、 **WM_HELP**メッセージです。  
  
-   **WS_EX_CONTROLPARENT** TAB キーを使用して、ウィンドウの子ウィンドウ間を移動することができます。  
  
-   **WS_EX_DLGMODALFRAME**二重の境界線は、タイトル バーを指定する場合に作成できます (オプション) を持つウィンドウを**WS_CAPTION**スタイル フラグを`dwStyle`パラメーター。  
  
-   **WS_EX_LAYERED**ウィンドウでは、[ウィンドウを階層化](http://msdn.microsoft.com/library/ms632599.aspx#layered)します。 ウィンドウを持つ場合、このスタイルは使用できません、[クラスのスタイル](http://msdn.microsoft.com/library/ms633574.aspx#class_styles)いずれかの**CS_OWNDC**または**CS_CLASSDC**します。 ただし、[!INCLUDE[win8_first](../../mfc/reference/includes/win8_first_md.md)]は、サポート、 **WS_EX_LAYERED** Windows の以前のバージョンのみサポートしてトップレベル ウィンドウの子ウィンドウのスタイル。  
  
-   **WS_EX_LEFT**ウィンドウ汎用左揃えプロパティを提供します。 既定値です。  
  
-   **WS_EX_LEFTSCROLLBAR**クライアント領域の左側に垂直スクロール バーを配置します。  
  
-   **WS_EX_LTRREADING**表示ウィンドウのテキストを左から右へを使用して読み取り順序プロパティです。 既定値です。  
  
-   **WS_EX_MDICHILD** MDI 子ウィンドウを作成します。  
  
-   **WS_EX_NOPARENTNOTIFY**このスタイルで作成された子ウィンドウは送信しないように指定、`WM_PARENTNOTIFY`子ウィンドウを作成または破棄されたときに、親ウィンドウへのメッセージ。  
  
-   **WS_EX_OVERLAPPEDWINDOW**を組み合わせて、 **WS_EX_CLIENTEDGE**と**WS_EX_WINDOWEDGE**スタイル  
  
-   **WS_EX_PALETTEWINDOW**を組み合わせて、 **WS_EX_WINDOWEDGE**と**WS_EX_TOPMOST**スタイル。  
  
-   **WS_EX_RIGHT**ウィンドウに汎用の右揃えプロパティを提供します。 これはウィンドウ クラスに依存します。  
  
-   **WS_EX_RIGHTSCROLLBAR**クライアント領域の右側に垂直スクロール バーを (ある場合) に配置します。 既定値です。  
  
-   **WS_EX_RTLREADING**ウィンドウを右から左への読み取りを使用してテキストの表示順序プロパティです。  
  
-   **WS_EX_STATICEDGE**をユーザー入力を受け取らない項目で使用するためのもので、3 d 境界線スタイルを持つウィンドウを作成します。  
  
-   **WS_EX_TOOLWINDOW**はウィンドウがフローティング ツールバーとして使用するためのツール ウィンドウを作成します。 ツール ウィンドウには、通常のタイトル バーより短いタイトル バーがあり、ウィンドウ タイトルは小さいフォントを使用して描画されます。 ツール ウィンドウは、タスク バーの中、またはユーザーが Alt + Tab キーを押したときに表示されるウィンドウには表示されません。  
  
-   **WS_EX_TOPMOST**このスタイルで作成したウィンドウがすべて上位ウィンドウに配置するウィンドウが非アクティブにいるときでもであることを指定します。 アプリケーションは `SetWindowPos` のメンバー関数を使用して、この属性を追加または削除することができます。  
  
-   **WS_EX_TRANSPARENT**このスタイルで作成したウィンドウが透明であることを指定します。 つまり、このウィンドウより奥にあるすべてのウィンドウは、このウィンドウによって隠されることはありません。 このスタイルで作成したウィンドウは、自らより奥にあるすべての兄弟ウィンドウが更新された後でのみ、`WM_PAINT` メッセージを受信します。  
  
-   **WS_EX_WINDOWEDGE**ウィンドウに、縁の罫線を指定します。  
  
## <a name="see-also"></a>関連項目  
 [MFC で使用するスタイル](../../mfc/reference/styles-used-by-mfc.md)   
 [とき](../../mfc/reference/cwnd-class.md#createex)   
 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)


