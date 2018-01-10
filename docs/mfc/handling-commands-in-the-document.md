---
title: "ドキュメント内のコマンドの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message maps [MFC], in document class
- command handling [MFC]
- documents [MFC], message maps
- message handling [MFC], WM_COMMAND messages
- command handling [MFC], commands in documents
- documents [MFC], handling messages in
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8d27698d573e1dee539f93ab88015285648fa77
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="handling-commands-in-the-document"></a>ドキュメントでのコマンドの処理
ドキュメント クラスでは、メニュー項目、ツール バー ボタン、またはアクセラレータ キーによって生成される特定のコマンドは処理も可能性があります。 既定では、 **CDocument**保存を処理し、シリアル化を使用して [ファイル] メニュー コマンドの名前を付けて保存します。 データに影響する他のコマンドは、ドキュメントのメンバー関数によっても処理できます。 たとえば、この Scribble プログラム クラス`CScribDoc`すべてをクリア編集のコマンドは、すべてのドキュメントに格納されているデータを削除するハンドラーを提供します。 ドキュメントは、メッセージ マップを持つことができますが、ビューとは異なり、ドキュメントが標準 Windows メッセージを処理できません-のみ**WM_COMMAND**メッセージ、または「コマンド」。  
  
## <a name="see-also"></a>参照  
 [ドキュメントの使い方](../mfc/using-documents.md)

