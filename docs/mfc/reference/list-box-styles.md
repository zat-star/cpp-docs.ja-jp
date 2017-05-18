---
title: "リスト ボックス スタイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LBS_STANDARD
- LBS_NODATA
- LBS_OWNERDRAWVARIABLE
- LBS_EXTENDEDSEL
- LBS_USETABSTOPS
- LBS_WANTKEYBOARDINPUT
- LBS_NOTIFY
- LBS_DISABLENOSCROLL
- LBS_HASSTRINGS
- LBS_NOREDRAW
- LBS_NOSEL
- LBS_NOINTEGRALHEIGHT
- LBS_MULTICOLUMN
- LBS_SORT
- LBS_MULTIPLESEL
- LBS_OWNERDRAWFIXED
dev_langs:
- C++
helpviewer_keywords:
- LBS_NOSEL constant
- LBS_NOREDRAW constant
- LBS_HASSTRINGS constant
- LBS_OWNERDRAWFIXED constant
- LBS_WANTKEYBOARDINPUT constant
- LBS_STANDARD constant
- LBS_MULTIPLESEL constant
- LBS_OWNERDRAWVARIABLE constant
- LBS_DISABLENOSCROLL constant
- LBS_NODATA constant
- list boxes, styles
- LBS_EXTENDEDSEL constant
- LBS_MULTICOLUMN constant
- LBS_NOTIFY constant
- LBS_USETABSTOPS constant
- LBS_NOINTEGRALHEIGHT constant
- LBS_SORT constant
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
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
ms.openlocfilehash: 8e038e5cef50bd15df85c9d7f8b213b54ed03825
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="list-box-styles"></a>リスト ボックス スタイル
-   **LBS_DISABLENOSCROLL**リスト ボックスが無効になっている、垂直スクロール バー、リスト ボックスにスクロールするには、十分な項目が含まれていない場合を示しています。 このスタイルが設定されていないと、項目が少なくてスクロールする必要がない場合、スクロール バーは表示されません。  
  
-   **LBS_EXTENDEDSEL**ユーザーは、SHIFT キーとマウス、または特殊なキーの組み合わせを使用して複数の項目を選択できます。  
  
-   **LBS_HASSTRINGS**文字列で構成される項目を格納するボックスのオーナー描画を指定します。 アプリケーションで使用できるように、メモリと文字列のポインターをリスト ボックスが保持、`GetText`の特定のアイテムのテキストを取得します。  
  
-   **LBS_MULTICOLUMN**が水平方向にスクロールされる基準を複数列のリスト ボックスを指定します。 `SetColumnWidth`メンバー関数は、列の幅を設定します。  
  
-   **LBS_MULTIPLESEL**文字列の選択が切り替えられたたびに、ユーザーがクリックするか、文字列をダブルクリックします。 文字列の任意の数を選択することができます。  
  
-   **LBS_NODATA**データを持たないリスト ボックスを指定します。 リスト ボックス内の項目の数が&1;,000 を超える場合は、このスタイルを指定します。 データを持たない一覧ボックスが必要、 **LBS_OWNERDRAWFIXED**スタイルを設定するは必要ありません、 **LBS_SORT**または**LBS_HASSTRINGS**スタイル。  
  
     データを持たないリスト ボックスではアイテムのデータを文字列またはビットマップが含まれていないする点を除いて、オーナー描画のリスト ボックスに似ています。 コマンドを追加するには、挿入、または項目を削除常にいずれかの指定した項目のデータを無視します。常に、リスト ボックス内の文字列を検索する要求が失敗します。 システムは、送信、`WM_DRAWITEM`項目を描画する必要があると、オーナー ウィンドウへのメッセージ。 ItemID メンバー、`DRAWITEMSTRUCT`で渡された構造体、`WM_DRAWITEM`メッセージが描画される項目の行番号を指定します。 データを持たないリスト ボックスを送信しません、`WM_DELETEITEM`メッセージです。  
  
-   **LBS_NOINTEGRALHEIGHT**リスト ボックスのサイズは、リスト ボックスが作成されたときに、アプリケーションで指定されたサイズと正確にします。 通常は、Windows は、リスト ボックスで一部の項目が表示されないように、リスト ボックスにサイズを変更します。  
  
-   **LBS_NOREDRAW**変更が加えられた場合、リスト ボックスの表示は更新されません。 このスタイルは、送信することによっていつでも変更できます、 **WM_SETREDRAW**メッセージです。  
  
-   **LBS_NOSEL**リスト ボックスに表示することができますが、選択されていない項目が含まれているかを指定します。  
  
-   **LBS_NOTIFY**親ウィンドウが、ユーザーがクリックするか、文字列をダブルクリックしたときに、入力メッセージを受信します。  
  
-   **LBS_OWNERDRAWFIXED**リスト ボックスの所有者がその内容を描画する必要はリスト ボックス内の項目を同じ高さ。  
  
-   **LBS_OWNERDRAWVARIABLE**リスト ボックスの所有者がその内容を描画する必要はリスト ボックス内の項目の高さの変数です。  
  
-   **LBS_SORT**リスト ボックス内の文字列はアルファベット順に並べ替えられます。  
  
-   **LBS_STANDARD**リスト ボックス内の文字列は、アルファベット順に並べ替えられ、親ウィンドウが、ユーザーがクリックするか、文字列をダブルクリックしたときに、入力メッセージを受信します。 リスト ボックスには、すべての側面に罫線が含まれています。  
  
-   **LBS_USETABSTOPS**を認識してその文字列を描画するときにタブ文字を展開するには、リスト ボックスを使用します。 既定のタブ位置は、32 ダイアログ単位です。 (ダイアログ単位は、水平または垂直距離です。 1 つの水平ダイアログ単位は、現在のダイアログ ベースの幅の単位の&4; 分の&1; と同じです。 ダイアログの基本単位は、高さ、および現在のシステム フォントの幅に基づいて計算されます。 **GetDialogBaseUnits** Windows の機能はピクセル単位で現在のダイアログ ボックスの基本単位を返します)。このスタイルを使用しないで**LBS_OWNERDRAWFIXED**します。  
  
-   **LBS_WANTKEYBOARDINPUT**リスト ボックスの所有者を受け取る`WM_VKEYTOITEM`または`WM_CHARTOITEM`リスト ボックスに入力フォーカスがある状態でキーを押したときのメッセージします。 これにより、キーボード入力で特別な処理を実行するアプリケーションです。  
  
## <a name="see-also"></a>関連項目  
 [MFC で使用するスタイル](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../../mfc/reference/clistbox-class.md#create)   
 [リスト ボックス スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775149)


