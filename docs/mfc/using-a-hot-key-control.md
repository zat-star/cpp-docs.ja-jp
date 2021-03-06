---
title: "ホット キー コントロールの使い方 |Microsoft ドキュメント"
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
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0a64de06d5bc499d5b566d6d40508d08e920264
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-hot-key-control"></a>ホット キー コントロールの使い方
ホット キー コントロールの一般的な使用方法は、次のパターンを次に示します。  
  
-   コントロールが作成されます。 コントロールがダイアログ ボックスのテンプレートで指定されている場合、ダイアログ ボックスの作成時に作成は自動です。 (必要、 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)ホット キー コントロールに対応するダイアログ クラスのメンバーです)。また、使用することができます、[作成](../mfc/reference/chotkeyctrl-class.md#create)メンバー関数を任意のウィンドウの子ウィンドウとして、コントロールを作成します。  
  
-   コントロールの既定値を設定する場合は、呼び出し、 [SetHotKey](../mfc/reference/chotkeyctrl-class.md#sethotkey)メンバー関数。 Shift キーを押し、特定の状態を禁止する場合は、呼び出す[SetRules](../mfc/reference/chotkeyctrl-class.md#setrules)です。 良いこれを行うには、ダイアログ ボックスで、コントロール ダイアログ ボックスの[OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)関数。  
  
-   ユーザーは、ホット キー コントロールにフォーカスがあるときに、ホット キーの組み合わせを押すことによって、コントロールとやり取りします。 ユーザーし、何らかの理由でことを示しますこのタスクが完了したこと、おそらく、ダイアログ ボックスにボタンをクリックします。  
  
-   このメンバー関数を使用する必要があります、プログラムが通知され、ユーザーがホット キーを選択したこと、 [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey)ホット キー コントロールから仮想キーと shift キーを押し状態の値を取得します。  
  
-   説明する方法のいずれかを使用して、ホット キーを設定することができます、ユーザーが選択したキーがわかったら、[ホット キーの設定](../mfc/setting-a-hot-key.md)です。  
  
-   ホット キー コントロールがダイアログ ボックスでは、場合、および`CHotKeyCtrl`オブジェクトは自動的に破棄されます。 かどうか、する必要はありません、両方のコントロールをことを確認して、`CHotKeyCtrl`オブジェクトが破棄されました。  
  
## <a name="see-also"></a>参照  
 [CHotKeyCtrl の使い方](../mfc/using-chotkeyctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

