---
title: "拡張コンボ ボックス コントロールの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 96903fabd5ec0a0cff4d55eb97e7d06271b79990
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="creating-an-extended-combo-box-control"></a>拡張コンボ ボックス コントロールの作成
拡張コンボ ボックス コントロールを作成する方法は、ダイアログ ボックスで、コントロールの使用か以外のウィンドウで作成するかによって異なります。  
  
### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>ダイアログ ボックスで直接 CComboBoxEx を使用するには  
  
1.  ダイアログ エディターでダイアログ テンプレート リソースを拡張コンボ ボックス コントロールを追加します。 そのコントロールの ID を指定します  
  
2.  拡張コンボ ボックス コントロールのプロパティ ダイアログ ボックスを使用して、必要に応じてスタイルを指定します。  
  
3.  使用して、[メンバー変数の追加ウィザード](../ide/adding-a-member-variable-visual-cpp.md)型のメンバー変数を追加する[CComboBoxEx](../mfc/reference/ccomboboxex-class.md)コントロールのプロパティにします。 このメンバーを使用するを呼び出すと`CComboBoxEx`メンバー関数。  
  
4.  [プロパティ] ウィンドウを使用して、任意拡張コンボ ボックス コントロールの通知メッセージを処理する必要がありますのダイアログ クラスのハンドラー関数にマップする (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。  
  
5.  [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)、その他のスタイルを設定、`CComboBoxEx`オブジェクト。  
  
### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>CComboBoxEx を以外のウィンドウで使用するには  
  
1.  ビューまたはウィンドウのクラスでは、コントロールを定義します。  
  
2.  コントロールの呼び出します[作成](../mfc/reference/ctabctrl-class.md#create)メンバー関数は、可能性のあるで[フィルターと並べ替え順序](../mfc/reference/cview-class.md#oninitialupdate)、親ウィンドウの可能性がありますの早期[OnCreate](../mfc/reference/cwnd-class.md#oncreate)ハンドラー関数。 コントロールのスタイルを設定します。  
  
## <a name="see-also"></a>関連項目  
 [CComboBoxEx の使い方](../mfc/using-ccomboboxex.md)   
 [コントロール](../mfc/controls-mfc.md)

