---
title: "静的コントロール スタイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SS_SUNKEN
- SS_CENTER
- SS_ENHMETAFILE
- SS_RIGHT
- SS_BLACKRECT
- SS_LEFTNOWORDWRAP
- SS_GRAYFRAME
- SS_USERITEM
- SS_GRAYRECT
- SS_WHITEFRAME
- SS_ETCHEDFRAME
- SS_ETCHEDVERT
- SS_WHITERECT
- SS_PATHELLIPSIS
- SS_WORDELLIPSIS
- SS_NOPREFIX
- SS_BITMAP
- SS_SIMPLE
- SS_CENTERIMAGE
- SS_BLACKFRAME
- SS_OWNERDRAW
- SS_REALSIZEIMAGE
- SS_RIGHTJUST
- SS_ICON
- SS_NOTIFY
- SS_ETCHEDHORZ
- SS_LEFT
- SS_ENDELLIPSIS
dev_langs:
- C++
helpviewer_keywords:
- SS_ICON constant
- SS_WHITEFRAME constant
- SS_BLACKFRAME constant
- SS_ETCHEDHORZ constant
- SS_OWNERDRAW constant
- SS_BITMAP constant
- SS_NOPREFIX constant
- SS_NOTIFY constant
- SS_CENTER constant
- SS_REALSIZEIMAGE constant
- SS_ETCHEDFRAME constant
- SS_CENTERIMAGE constant
- SS_SUNKEN constant
- SS_ENDELLIPSIS constant
- SS_WORDELLIPSIS constant
- SS_WHITERECT constant
- SS_ETCHEDVERT constant
- SS_GRAYFRAME constant
- SS_LEFTNOWORDWRAP constant
- SS_LEFT constant
- SS_SIMPLE constant
- static styles
- SS_ENHMETAFILE constant
- SS_GRAYRECT constant
- SS_USERITEM constant
- SS_PATHELLIPSIS constant
- SS_BLACKRECT constant
- SS_RIGHT constant
- SS_RIGHTJUST constant
ms.assetid: a1114548-fc6d-491d-8c46-21d11b8574f5
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ad34c688fdfd3c2b4c81a0a03fbce53a905162ad
ms.lasthandoff: 02/24/2017

---
# <a name="static-styles"></a>静的コントロール スタイル
-   **SS_BITMAP**静的コントロールに表示されるビットマップを指定します。 指定したテキストは、リソース ファイルで定義されているビットマップ (名) の名前です。 スタイル、nWidth とパラメーター nHeight パラメーターは無視されます。コントロールでは、ビットマップが収まるように自動的にサイズします。  
  
-   **SS_BLACKFRAME**ウィンドウ フレームと同じ色で描画されたフレームを使用して、ボックスを指定します。 既定値は黒です。  
  
-   **SS_BLACKRECT**ウィンドウ フレームの描画に使用する色で塗りつぶされた四角形を指定します。 既定値は黒です。  
  
-   **SS_CENTER**単純な四角形を指定し、四角形の中央に指定したテキストが表示されます。 テキストの書式が表示されるようにします。 行の末尾を越えると単語は、次の中央の行の先頭に自動的に折り返されます。  
  
-   **SS_CENTERIMAGE**ビットマップやアイコンのスタティック コントロールのクライアント領域よりも小さい場合は場合、に、クライアント領域の残りの部分がビットマップやアイコンの左上隅にあるピクセルの色で塗りつぶされたことを指定します。 静的コントロールに&1; 行のテキストが含まれている場合、コントロールのクライアント領域内のテキストが垂直方向に中央揃えです。  
  
-   **SS_ENDELLIPSIS**または**SS_PATHELLIPSIS**結果が指定された四角形に収まるように、必要に応じて、省略記号を指定した文字列の一部が置き換えられます。  
  
     指定できます**SS_END_ELLIPSIS** 、文字列の末尾の文字を置換または**SS_PATHELLIPSIS**文字列の途中で文字を置換します。 文字列に円記号が含まれている場合 (\\) 文字、 **SS_PATHELLIPSIS**を保持できるだけ多くのテキストの最後のバック スラッシュの後に、できるだけします。  
  
-   **SS_ENHMETAFILE**拡張メタファイルが静的コントロールに表示されることを指定します。 指定したテキストは、メタファイルの名前です。 拡張メタファイル静的コントロールが固定サイズです。メタファイルは静的コントロールのクライアント領域に合わせてスケーリングされます。  
  
-   **SS_ETCHEDFRAME**を使用して、スタティック コントロールの枠を描画、 **EDGE_ETCHED**エッジのスタイル。  
  
-   **SS_ETCHEDHORZ**を使用して、スタティック コントロールの上端と下端の縁を描画、 **EDGE_ETCHED**エッジのスタイル。  
  
-   **SS_ETCHEDVERT** EDGE_ETCHED 端のスタイルを使用して静的コントロールの左端と右端の縁を描画します。  
  
-   **SS_GRAYFRAME**画面の背景 (デスクトップ) と同じ色で描画されたフレームを使用して、ボックスを指定します。 既定値は灰色です。  
  
-   **SS_GRAYRECT**画面の背景の塗りつぶしに使用する色で塗りつぶされた四角形を指定します。 既定値は灰色です。  
  
-   **SS_ICON**  ダイアログ ボックスに表示されるアイコンを指定します。 指定したテキストは、リソース ファイルで定義されているアイコン (名) の名前です。 `nWidth`と`nHeight`パラメーターは無視されます。 自動的に、アイコンのサイズ。  
  
-   **SS_LEFT**単純な四角形を指定し、指定された四角形の左揃えテキストが表示されます。 テキストの書式が表示されるようにします。 行の末尾を越えると単語は、左揃えの次の行の先頭に自動的に折り返されます。  
  
-   **SS_LEFTNOWORDWRAP**単純な四角形を指定し、指定された四角形の左揃えテキストが表示されます。 タブが展開されているが、テキストは折り返されません。 行の末尾を超える長さのテキストが切り取られます。  
  
-   **SS_NOPREFIX** Windows がアクセラレータ プレフィックス文字をコントロールのテキストに含まれるアンパサンド (&) の文字を解釈このスタイルを指定しない限り、します。 この場合は、アンパサンドが削除され、文字列内の次の文字に下線が引かれます。 静的コントロールがテキストを格納する、この機能は必要ではない場合、 **SS_NOPREFIX**追加することもできます。 この静的コントロール スタイルは、定義済みのスタティック コントロールのいずれかを含めることができます。 組み合わせることができます**SS_NOPREFIX**ビットごとの OR 演算子を使用して、その他のスタイルを使用します。 アンパサンドを含む可能性のあるその他の文字列またはファイル名 ダイアログ ボックスで静的コントロールに表示する必要がある場合に最もよく使用されるオプションです。  
  
-   **SS_NOTIFY**親ウィンドウに送信**STN_CLICKED**、 **STN_DBLCLK**、 **STN_DISABLE**、および**STN_ENABLE**の通知メッセージをクリックするか、コントロールをダブルクリックするとします。  
  
-   **SS_OWNERDRAW**のスタティック コントロールの所有者がコントロールの描画を担当することを指定します。 オーナー ウィンドウは、`WM_DRAWITEM`コントロールを描画する必要があるときのメッセージします。  
  
-   **SS_REALSIZEIMAGE**により、静的なアイコンまたはビットマップ コントロール (を持つ静的コントロールは、 **SS_ICON**または**SS_BITMAP**スタイル) のようにロードされるか、描画されるサイズを変更します。 アイコンまたはビットマップがコピー先領域よりも大きい場合、イメージが切り取られます。  
  
-   **SS_RIGHT**単純な四角形を指定し、指定したテキストの四角形にフラッシュ右側を表示します。 テキストの書式が表示されるようにします。 行の末尾を越えると単語は、フラッシュ右の次の行の先頭に自動的に折り返されます。  
  
-   **SS_RIGHTJUST**ことが指定された静的コントロールの右下隅、 **SS_BITMAP**または**SS_ICON**スタイルが引き続きコントロールのサイズを固定します。 上と左の辺は、新しいビットマップやアイコンに合わせて調整されます。  
  
-   **SS_SIMPLE**単純な四角形を指定し、単一の行の四角形の左揃えのテキストが表示されます。 行のテキストを簡略化され、または変更されることできません。 (コントロールの親ウィンドウまたはダイアログ ボックスを処理する必要があります、`WM_CTLCOLOR`メッセージです)。  
  
-   **SS_SUNKEN**スタティック コントロール周囲の半分くぼんだ境界線を描画します。  
  
-   **SS_USERITEM**ユーザー定義の項目を指定します。  
  
-   **SS_WHITEFRAME**ウィンドウの背景色と同じ色で描画されたフレームを使用して、ボックスを指定します。 既定の色は白です。  
  
-   **SS_WHITERECT**ウィンドウの背景の塗りつぶしに使用する色で塗りつぶされた四角形を指定します。 既定の色は白です。  
  
-   **SS_WORDELLIPSIS**収まらない場合、省略記号を追加するテキストが切り捨てられます。  
  
## <a name="see-also"></a>関連項目  
 [MFC で使用するスタイル](../../mfc/reference/styles-used-by-mfc.md)   
 [CStatic::Create](../../mfc/reference/cstatic-class.md#create)   
 [DrawEdge](http://msdn.microsoft.com/library/windows/desktop/dd162477)   
 [静的コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760773)


