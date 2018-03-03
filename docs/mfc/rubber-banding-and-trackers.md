---
title: "ラバー バンド処理とトラッカー |Microsoft ドキュメント"
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
- trackers [MFC]
- CRectTracker class [MFC], implementing trackers
- OLE objects [MFC], selecting
- rubber banding [MFC]
- WM_LBUTTONDOWN [MFC]
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3bd9da00d2d6ea0110562f523a0adc53c1a476c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="rubber-banding-and-trackers"></a>ラバー バンド処理とトラッカー
トラッカーに付属している別の機能は、「ラバー バンド」の選択 を選択するアイテムの周囲のサイズ変更四角形をドラッグして複数の OLE 項目を選択することが可能です。 ユーザーがマウスの左ボタンを離したときに、ユーザーが選択されている地域内の項目が選択され、ユーザーが操作することができます。 たとえば、ユーザーは、別のコンテナー アプリケーションへ、選択をドラッグする可能性があります。  
  
 いくつか追加のコードで、アプリケーションのこの機能を実装する必要があります`WM_LBUTTONDOWN`ハンドラー関数。  
  
 次のコード サンプルは、ラバー バンドの選択と追加機能を実装します。  
  
 [!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]  
  
 ラバー バンド処理中に、トラッカーの方向の元に戻すことを許可する場合を呼び出す必要があります[CRectTracker::TrackRubberBand](../mfc/reference/crecttracker-class.md#trackrubberband) 3 番目のパラメーターを設定した**TRUE**です。 印刷の向きを元に戻すことを許可するがなることがあります[裏返し](../mfc/reference/crecttracker-class.md#m_rect)になるとは逆にします。 これへの呼び出しによって修正できる[CRect::NormalizeRect](../atl-mfc-shared/reference/crect-class.md#normalizerect)です。  
  
 詳細については、次を参照してください。[コンテナー クライアント アイテム](../mfc/containers-client-items.md)と[のカスタマイズのドラッグ アンド ドロップ](../mfc/drag-and-drop-customizing.md)です。  
  
## <a name="see-also"></a>参照  
 [トラッカー: OLE アプリケーションでのトラッカーの実装](../mfc/trackers-implementing-trackers-in-your-ole-application.md)   
 [CRectTracker クラス](../mfc/reference/crecttracker-class.md)
