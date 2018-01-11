---
title: "ヘッダー項目に対するドラッグ アンド ドロップのサポートを提供する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fd1ac2171a13610ee3aeabed12f5348089a57491
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>ヘッダー項目に対するドラッグ アンド ドロップのサポート
ヘッダー項目に対するドラッグ アンド ドロップのサポートを提供する指定、`HDS_DRAGDROP`スタイル。 ヘッダー項目に対するドラッグ アンド ドロップのサポートは、ヘッダー コントロールのヘッダー項目の順序を変更する機能をユーザーに与えます。 既定の動作は、ヘッダー項目が削除された場合、ドラッグされているヘッダー項目の半透明のドラッグ イメージと、新しい位置の視覚インジケーターを提供します。  
  
 一般的なドラッグ アンド ドロップ機能により、処理することにより既定のドラッグ アンド ドロップの動作を拡張することができますと、 **HDN_BEGINDRAG**と**HDN_ENDDRAG**通知します。 オーバーライドすることで、ドラッグ イメージの外観をカスタマイズすることも、 [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage)メンバー関数。  
  
> [!NOTE]
>  埋め込みヘッダー内のコントロール リスト コントロールをドラッグ アンド ドロップのサポートを提供する場合は、拡張スタイル」を参照してください、[リスト コントロール スタイルの変更](../mfc/changing-list-control-styles.md)トピックです。  
  
## <a name="see-also"></a>参照  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)

