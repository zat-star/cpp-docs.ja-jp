---
title: "CTreeCtrl の vs です。CTreeView |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CTreeCtrl
- CTreeView
dev_langs: C++
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bb0c1b7a7bf73ab70bbccca6f2a9ccc2ab385516
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl の vs です。CTreeView
MFC には、ツリー コントロールをカプセル化する 2 つのクラスが用意されています: [CTreeCtrl](../mfc/reference/ctreectrl-class.md)と[CTreeView](../mfc/reference/ctreeview-class.md)です。 各クラスは、さまざまな状況で役に立ちます。  
  
 使用して`CTreeCtrl`プレーンな子ウィンドウ コントロールである必要がある場合、ダイアログ ボックスでのインスタンス。 使用する場合は特に`CTreeCtrl`がある場合以外の子コントロール] ウィンドウで、一般的なダイアログ ボックスと同様にします。  
  
 使用して`CTreeView`する必要がある場合、ツリーのコントロールだけでなく、ツリー コントロールにドキュメント/ビュー アーキテクチャ [ビュー] ウィンドウと同様に動作します。 A`CTreeView`のフレーム ウィンドウまたは分割ウィンドウ全体のクライアント領域を占有します。 自動的にサイズを変更、親ウィンドウのサイズを変更し、メニューのアクセラレータ キー、およびツールバーからコマンド メッセージを処理するときにします。 ツリー コントロールにツリーを表示するために必要なデータが含まれているため、対応するドキュメント オブジェクトする必要はありません複雑になる — も[CDocument](../mfc/reference/cdocument-class.md)ドキュメント テンプレートにドキュメントの種類として。  
  
## <a name="see-also"></a>参照  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

