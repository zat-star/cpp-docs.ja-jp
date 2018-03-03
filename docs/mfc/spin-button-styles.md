---
title: "スピン ボタンのスタイル |Microsoft ドキュメント"
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
- styles [MFC], CSpinButtonCtrl
- CSpinButtonCtrl class [MFC], styles
- styles [MFC], spin button control
- spin button control, styles
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa4b2ae42175e2d4fc2ddb3317ef76b6b4dec8d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="spin-button-styles"></a>スピン ボタンのスタイル
スピン ボタンの設定の多く ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) スタイルによって制御されます。 使用して、次のスタイルを設定することができます、**プロパティ**ダイアログ エディターのウィンドウ。  
  
-   **印刷の向き**垂直または水平方向のいずれか。 矢印ボタンの方向を制御します。 関連付けられている、`UDS_HORZ`スタイル。  
  
-   **配置**結び付けられていない、左右のいずれか。 スピン ボタンの場所を制御します。 Left と Right は、関連ウィンドウの横にあるスピン ボタンを配置します。 スピン ボタンに対応する関連ウィンドウの幅を縮小します。 関連付けられている、`UDS_ALIGNLEFT`と`UDS_ALIGNRIGHT`スタイル。  
  
-   **Auto Buddy**スピン ボタンの連動ウィンドウとして Z オーダーで前のウィンドウを自動的に選択します。 ダイアログ テンプレートで、これは、スピン ボタンの前に、タブ オーダーのコントロールです。 関連付けられている、`UDS_AUTOBUDDY`スタイル。  
  
-   **設定 Buddy Integer**スピン コントロールをインクリメントおよび現在の位置の変更と連動ウィンドウのキャプションをデクリメントします。 関連付けられている、`UDS_SETBUDDYINT`スタイル。  
  
-   **Nothousands**桁は挿入されませんが連動ウィンドウのキャプションの値の区切り記号。 関連付けられている、`UDS_NOTHOUSANDS`スタイル。  
  
    > [!NOTE]
    >  ダイアログ データ エクス (チェンジ DDX) を使用して、アップダウン コントロールからの整数値を取得する場合は、このスタイルを設定します。 `DDX_Text`埋め込みの桁区切り記号は受け入れられません。  
  
-   **ラップ**によって「ラップ」値がインクリメントまたはデクリメント コントロールの範囲外に位置します。 関連付けられている、`UDS_WRAP`スタイル。  
  
-   **方向キー**スピン ボタンの上方向キーおよび ↓ キーが押されたときに、位置を増減します。 関連付けられている、`UDS_ARROWKEYS`スタイル。  
  
## <a name="see-also"></a>参照  
 [CSpinButtonCtrl の使い方](../mfc/using-cspinbuttonctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

