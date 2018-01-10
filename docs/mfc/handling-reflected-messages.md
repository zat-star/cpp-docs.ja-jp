---
title: "反映されたメッセージの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0c3576e93ce7ce2d972e78433065feaf06f3ae15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="handling-reflected-messages"></a>反映されたメッセージの処理方法
リフレクションを使用してなど、コントロールのメッセージを処理できるメッセージ`WM_CTLCOLOR`、 **WM_COMMAND**、および**WM_NOTIFY**、コントロール自体の内部です。 これによってより自己完結してポータブル コントロール。 メカニズムは、Windows のコモン コントロール、および ActiveX コントロール (旧称 OLE コントロール) では動作します。  
  
 メッセージ リフレクションでは、再利用することができます、 `CWnd`-派生クラスをより容易にします。 メッセージのリフレクションの動作を使用して[CWnd::OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify)、特別なを使用して**ON_XXX_REFLECT**メッセージ マップ エントリ: たとえば、 **ON_CTLCOLOR_REFLECT**と**ON_CONTROL_REFLECT**です。 [テクニカル ノート 62](../mfc/tn062-message-reflection-for-windows-controls.md)さらに詳しくメッセージ リフレクションについて説明します。  
  
## <a name="what-do-you-want-to-do"></a>どうしたいんですか  
  
-   [詳細については、メッセージ リフレクション](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [コモン コントロールの実装のメッセージ リフレクション](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [ActiveX コントロールの実装のメッセージ リフレクション](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)  
  
## <a name="see-also"></a>参照  
 [メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)
