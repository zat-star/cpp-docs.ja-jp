---
title: "ツールバーの作成方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CToolBarCtrl class [MFC], and CToolBar class [MFC]
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- toolbar controls [MFC]
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d93f8e43c933e9c8054e798c11754cc48bf54a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="methods-of-creating-a-toolbar"></a>ツール バーの作成方法
MFC には、ツールバーを作成する 2 つのクラスが用意されています: [CToolBar](../mfc/reference/ctoolbar-class.md)と[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) (をラップする Windows のコモン コントロール API)。 `CToolBar`すべてのツール バー コモン コントロールの機能を提供する; の必要な共通コントロールの設定と構造の多くを処理し、ただし、実行可能ファイル、通常はより大きくするを使用して作成`CToolBarCtrl`です。  
  
 `CToolBarCtrl`通常、小規模な実行可能ファイルに結果が利用しやすい`CToolBarCtrl`MFC アーキテクチャにツールバーを統合する予定がない場合。 使用する場合`CToolBarCtrl`MFC アーキテクチャにツールバーを統合して、mfc ツールバー コントロールの操作を通信するために十分注意を行う必要があります。 この通信が困難です。ただしは、使用する場合、必要な追加の作業が`CToolBar`です。  
  
 Visual C には、ツール バー コモン コントロールを活用するために 2 つの方法が用意されています。  
  
-   ツールバーを使用して、作成`CToolBar`、まず[CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl)へのアクセスを取得する、`CToolBarCtrl`メンバー関数。  
  
-   ツールバーを使用して、作成[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)のコンス トラクターです。  
  
 どちらの方法でもにアクセスできますツール バー コントロールのメンバー関数。 呼び出すと`CToolBar::GetToolBarCtrl`への参照を返します、`CToolBarCtrl`オブジェクトのメンバー関数の両方のセットを使用できるようにします。 参照してください[CToolBar](../mfc/reference/ctoolbar-class.md)を構築してを使用して、ツールバーの作成について`CToolBar`です。  
  
## <a name="see-also"></a>参照  
 [CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

