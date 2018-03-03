---
title: "コマンド ルーティングの図 |Microsoft ドキュメント"
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
- MFC, command routing
- command handling [MFC], routing commands
- command routing [MFC], OnCmdMsg handler
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24ac591005d5df6b18102d296352b8b2528ba839
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="command-routing-illustration"></a>コマンド ルーティングの図
理解するには、MDI アプリケーションの編集] メニューの [すべてクリア メニュー項目からのコマンド メッセージを検討してください。 このコマンドのハンドラー関数の処理は、アプリケーションのドキュメント クラスのメンバー関数であるとします。 次にそのコマンドが、ユーザーがメニュー項目を選択した後にそのハンドラーをどのように到達方法を示します。  
  
1.  メイン フレーム ウィンドウは、コマンド メッセージを最初に受け取ります。  
  
2.  メイン MDI フレーム ウィンドウは、現在アクティブな MDI 子ウィンドウにコマンドを処理する機会を与えます。  
  
3.  MDI 子フレーム ウィンドウの標準のルーティングにより、そのビュー コマンドを独自のメッセージ マップをチェックする前にできます。  
  
4.  ビューでは、まずメッセージ マップがチェックされ、関連付けられたドキュメントに、コマンドをルーティング次に、ハンドラーが見つからない。  
  
5.  ドキュメントは、メッセージ マップを確認し、ハンドラーを検索します。 ドキュメントのメンバー関数が呼び出され、転送が終了します。  
  
 ドキュメントには、ハンドラーがないには次のコマンドをルーティングはドキュメント テンプレートにします。 コマンドは、ビューと、フレーム ウィンドウに戻ります。 最後に、フレーム ウィンドウは、メッセージ マップをチェックインします。 メイン MDI フレーム ウィンドウに、アプリケーション オブジェクトにし、コマンドがルーティング確認が失敗した場合も、: ハンドルされていないコマンドの最終的な送信先です。  
  
## <a name="see-also"></a>参照  
 [フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)

