---
title: "ウィンドウ プロシージャ エントリ ポイント |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5f4e99ce38bd5ae472d688dc779bdd4ccf9fd4c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="window-procedure-entry-points"></a>ウィンドウ プロシージャのエントリ ポイント
MFC のウィンドウ プロシージャ、特殊なウィンドウ プロシージャの実装とモジュールの静的リンクを保護します。 リンケージは、MFC とリンクすると、モジュールと自動的に発生します。 このウィンドウ プロシージャを使用して、`AFX_MANAGE_STATE`マクロを呼び出し、有効なモジュールの状態を正しく設定**プロシージャ**、順番にデリゲートを、`WindowProc`メンバー関数は、適切な`CWnd`-派生。オブジェクト。  
  
## <a name="see-also"></a>参照  
 [MFC モジュールの状態データの管理](../mfc/managing-the-state-data-of-mfc-modules.md)

