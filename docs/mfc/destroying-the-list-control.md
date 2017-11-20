---
title: "リスト コントロールの破棄 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 069d9eddc44aa4c0f258f97fce1e39266ced95b6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="destroying-the-list-control"></a>リスト コントロールの破棄
埋め込む場合、 [CListCtrl](../mfc/reference/clistctrl-class.md)オブジェクト ビューまたはダイアログのクラスのデータ メンバーとしてその所有者が破棄されるときは破棄されます。 使用する場合、 [CListView](../mfc/reference/clistview-class.md)ビューが破棄されると、フレームワークが、コントロールを破棄します。  
  
 リスト コントロールではなく、アプリケーションに格納される、リストのデータの一部に基づいて並べ替えた場合は、メモリを解放を配置する必要があります。 詳細については、次を参照してください。[コールバック項目とコールバック マスク](http://msdn.microsoft.com/library/windows/desktop/bb774736)Windows SDK に含まれています。  
  
 さらに、ユーザーはイメージ リストを作成し、リスト コントロール オブジェクトに関連付けられているも解放担当します。  
  
## <a name="see-also"></a>関連項目  
 [CListCtrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

