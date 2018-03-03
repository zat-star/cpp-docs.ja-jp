---
title: "CStatusBarCtrl オブジェクトでツールヒントを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf522d17d8abfc4b8dbf53baa24255ab23cfa621
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>CStatusBarCtrl オブジェクトでのツール ヒントの使い方
ステータス バー コントロールにツールヒントを有効にするには、作成、`CStatusBarCtrl`オブジェクトを**には**スタイル。  
  
> [!NOTE]
>  使用している場合、`CStatusBar`を使用して、ステータス バーを実装するオブジェクト、`CStatusBar::CreateEx`関数。 埋め込みの追加のスタイルを指定することができます**CStatusBarCtrl**オブジェクト。  
  
 1 回、`CStatusBarCtrl`オブジェクトが正常に作成されるを使用して[CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext)と[CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext)設定と特定のウィンドウに関するツールヒントのテキストを取得します。  
  
 ツール ヒントを設定すると、パーツ内のすべてのテキストを表示できない場合または部分がある、アイコンとテキストがない場合にのみ表示されます。 ツール ヒントは簡易モードではサポートされていません。  
  
## <a name="see-also"></a>参照  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

