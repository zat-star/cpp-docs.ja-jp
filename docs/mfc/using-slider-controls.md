---
title: "スライダー コントロールを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4fdab6a7fae25845da81ee7263e045e50951f557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-slider-controls"></a>スライダー コントロールの使い方
通常、スライダー コントロールの使い方は、次のパターンを次に示します。  
  
-   コントロールが作成されます。 コントロールがダイアログ ボックスのテンプレートで指定されている場合、ダイアログ ボックスの作成時に作成は自動です。 (必要、 [CSliderCtrl](../mfc/reference/csliderctrl-class.md)スライダー コントロールに対応するダイアログ クラスのメンバーです)。また、使用することができます、[作成](../mfc/reference/csliderctrl-class.md#create)メンバー関数を任意のウィンドウの子ウィンドウとして、コントロールを作成します。  
  
-   コントロールの値を設定する、さまざまなセットのメンバー関数を呼び出します。 変更行うことができますにはには、スライダーの最小値と最大位置を設定、目盛りを描画、選択範囲の設定、スライダーの位置が含まれます。 これを行う絶好のタイミングは、ダイアログ ボックスで、コントロール ダイアログ ボックスの[OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)関数。  
  
-   ユーザー対話するので、コントロールで、さまざまな通知メッセージが送信されます。 コントロールからスライダーの値を抽出するには呼び出すことによって、 [GetPos](../mfc/reference/csliderctrl-class.md#getpos)メンバー関数。  
  
-   コントロールに完了したらが正常に破棄されるかどうかを確認する必要があります。 スライダー コントロールがダイアログ ボックスでは、場合、および`CSliderCtrl`オブジェクトは自動的に破棄されます。 かどうか、する必要はありません、両方のコントロールをことを確認して、`CSliderCtrl`オブジェクトが破棄されました。  
  
## <a name="see-also"></a>参照  
 [CSliderCtrl の使い方](../mfc/using-csliderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

