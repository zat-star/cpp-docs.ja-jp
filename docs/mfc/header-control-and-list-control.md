---
title: "ヘッダー コントロールおよびリスト コントロール |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListCtrl class [MFC], with CHeaderCtrl
- CListCtrl class [MFC], header controls
- CHeaderCtrl class [MFC], with CListCtrl
- controls [MFC], header
- header controls [MFC]
- header controls [MFC], list controls used with
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 213d2eeec7628c54d68bbd8f636ae85d90e7e8de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="header-control-and-list-control"></a>ヘッダー コントロールおよびリスト コントロール
ほとんどの場合に埋め込まれているヘッダー コントロールを使用して、 [CListCtrl](../mfc/reference/clistctrl-class.md)または[CListView](../mfc/reference/clistview-class.md)オブジェクト。 ただし、別のヘッダー コントロール オブジェクトが内の行または列に配置されたデータを操作するなど、望ましい場合がある、 [CView](../mfc/reference/cview-class.md)-派生オブジェクト。 このような場合は、埋め込みヘッダー コントロールの既定の動作と外観を細かく制御する必要があります。  
  
 ヘッダー コントロールを標準を提供する多くの場合、既定の動作を使用する場合は、 [CListCtrl](../mfc/reference/clistctrl-class.md)または[CListView](../mfc/reference/clistview-class.md)代わりにします。 使用して`CListCtrl`リスト ビューのコモン コントロールに埋め込まれている既定のヘッダー コントロールの機能を使用する場合。 使用して[CListView](../mfc/reference/clistview-class.md)ビュー オブジェクトに埋め込まれている既定のヘッダー コントロールの機能を使用する場合。  
  
> [!NOTE]
>  これらのコントロールにはのみが含まれて、組み込みのヘッダー コントロールには使用してリスト ビュー コントロールを作成する場合、`LVS_REPORT`スタイル。  
  
 ほとんどの場合を含むリスト ビュー コントロールのスタイルを変更することによって埋め込みヘッダー コントロールの外観を変更できます。 さらに、ヘッダー コントロールの概要については、親のリスト ビュー コントロールのメンバー関数を使用して取得できます。 ただし、完全に制御および属性と埋め込みヘッダー コントロールのスタイルへのアクセスには、ヘッダー コントロール オブジェクトへのポインターを取得することをお勧めします。  
  
 埋め込みのヘッダー コントロール オブジェクトは、いずれかからアクセスできる**CListCtrl**または`CListView`、それぞれのクラスを呼び出して`GetHeaderCtrl`メンバー関数。 次のコードでは、これを示しています。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [イメージ リストのヘッダー コントロールの使い方](../mfc/using-image-lists-with-header-controls.md)  
  
## <a name="see-also"></a>参照  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

