---
title: "メッセージ ハンドラー |Microsoft ドキュメント"
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
- message handlers [MFC]
- command handling [MFC], message handlers
- handlers [MFC]
- message handling [MFC], message handler functions
- handlers [MFC], command
- handlers [MFC], message
ms.assetid: 51bc4e76-dbe3-4cc2-b026-3199d56b2fa9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d1b906a49d7da7ed8505252a1759d7ea00fcda1f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="message-handlers"></a>メッセージ ハンドラー
MFC では、専用*ハンドラー*関数は、各メッセージを処理します。 メッセージ ハンドラー関数は、クラスのメンバー関数です。 このドキュメントでは、用語*メッセージ ハンドラー メンバー関数は、*、*メッセージ ハンドラー関数*、*メッセージ ハンドラー*、および*ハンドラー*同義です。 一部のメッセージ ハンドラーとも呼ばれます「コマンド ハンドラー」  
  
 フレームワーク アプリケーションの作成には、作業の大部分を占めてメッセージ ハンドラーのアカウントを書き込んでいます。 ここでは、メッセージ処理のメカニズムの動作方法について説明します。  
  
 メッセージのハンドラーは、何が必要なあらゆるそのメッセージを応答で元に戻す。 クラスのプロパティ ウィンドウを使用してハンドラーを作成し、ソース コード エディターを使用して、ハンドラーのコードを入力できます。  
  
 ハンドラーを記述するのにには、すべての Microsoft Visual C と MFC の機能を使用できます。 すべてのクラスの一覧は、次を参照してください。[クラス ライブラリの概要](../mfc/class-library-overview.md)で、 *『 MFC リファレンス*です。  
  
## <a name="see-also"></a>参照  
 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

