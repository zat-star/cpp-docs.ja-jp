---
title: "予定表コントロールの月を作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f55960177fa8bc9a31ebfd16b4dbc6aeaba3ee38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-month-calendar-control"></a>月間予定表コントロールの作成
月間予定表コントロールの作成方法は、ダイアログ ボックスで、コントロールの使用か以外のウィンドウで作成するかによって異なります。  
  
### <a name="to-use-cmonthcalctrl-directly-in-a-dialog-box"></a>ダイアログ ボックスで直接 CMonthCalCtrl を使用するには  
  
1.  ダイアログ エディターでダイアログ テンプレート リソースを月間予定表コントロールを追加します。 そのコントロールの ID を指定します  
  
2.  月間予定表コントロールのプロパティ ダイアログ ボックスを使用して、必要に応じてスタイルを指定します。  
  
3.  使用して、[メンバー変数の追加ウィザード](../ide/adding-a-member-variable-visual-cpp.md)型のメンバー変数を追加する[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)コントロールのプロパティにします。 このメンバーを使用するを呼び出すと`CMonthCalCtrl`メンバー関数。  
  
4.  使用任意月間予定表コントロールの通知のダイアログ クラスのハンドラー関数にマップする [プロパティ] ウィンドウを処理する必要があります (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。  
  
5.  [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)、その他のスタイルを設定、`CMonthCalCtrl`オブジェクト。  
  
### <a name="to-use-cmonthcalctrl-in-a-nondialog-window"></a>以外のウィンドウで関数を使用するには  
  
1.  ビューまたはウィンドウのクラスでは、コントロールを定義します。  
  
2.  コントロールの呼び出します[作成](../mfc/reference/cmonthcalctrl-class.md#create)メンバー関数は、可能性のあるで[フィルターと並べ替え順序](../mfc/reference/cview-class.md#oninitialupdate)、親ウィンドウの可能性がありますの早期[OnCreate](../mfc/reference/cwnd-class.md#oncreate)ハンドラー関数 (ユーザー場合サブクラス化コントロール)。 コントロールのスタイルを設定します。  
  
## <a name="see-also"></a>参照  
 [CMonthCalCtrl の使い方](../mfc/using-cmonthcalctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

