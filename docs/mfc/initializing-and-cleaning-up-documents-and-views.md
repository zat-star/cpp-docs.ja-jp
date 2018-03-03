---
title: "ドキュメントとビューの初期化と後処理 |Microsoft ドキュメント"
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
- initializing documents [MFC]
- views [MFC], cleaning up
- documents [MFC], initializing
- documents [MFC], cleaning up
- views [MFC], initializing
- initializing objects [MFC], document objects
- document objects [MFC], life cycle of
- initializing views [MFC]
ms.assetid: 95d6f09b-a047-4079-856a-ae7d0548e9d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0546bfc0a5226c6cd22497acae1bb364ceba107b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>ドキュメントとビューの初期化と後処理
初期化し、ドキュメントとビューの後にクリーンアップするため、次のガイドラインを使用します。  
  
-   MFC フレームワークは、ドキュメントとビューを初期化します。追加するすべてのデータを初期化するとします。  
  
-   フレームワークのドキュメントとしてクリーンアップし、ビューを閉じます。ドキュメントとビューのメンバー関数の中からヒープに割り当てられたメモリの割り当てを解除する必要があります。  
  
> [!NOTE]
>  アプリケーション全体がのオーバーライドで最適な方法はの初期化を取り消し、 [InitInstance](../mfc/reference/cwinapp-class.md#initinstance)クラスのメンバー関数`CWinApp`、アプリケーション全体のクリーンアップは、のオーバーライドで最適な方法は、`CWinApp`メンバー関数は、 [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance)です。  
  
 ドキュメントとそのフレーム ウィンドウとビュー (ビュー) mdi のライフ サイクル アプリケーションのとおりです。  
  
1.  動的の作成時にドキュメントのコンス トラクターが呼び出されます。  
  
2.  各新しいドキュメントに、ドキュメントの[でも実質的](../mfc/reference/cdocument-class.md#onnewdocument)または[かまいません](../mfc/reference/cdocument-class.md#onopendocument)と呼びます。  
  
3.  ユーザーは、その有効期間中のドキュメントを操作します。 これは通常、ユーザーに合わせて、ビューを使用してドキュメント データを選択して、データを編集します。 ビューには、変更を記憶域と他のビューの更新のドキュメントが渡されます。 この期間中に、ドキュメントとビューの両方がコマンドを処理できます。  
  
4.  フレームワークによって[DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)をドキュメントに固有のデータを削除します。  
  
5.  ドキュメントのデストラクターは呼び出されます。  
  
 SDI アプリケーションでは、ドキュメントを最初に作成した後は、手順 1 は実行されます。 手順 2 ~ 4 は、繰り返し実行、新しいドキュメントが開かれるたびにします。 この新しいドキュメントには、既存のドキュメント オブジェクトが再利用します。 最後に、手順 5 では、アプリケーションの終了時に実行されます。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ドキュメントとビューの初期化](../mfc/initializing-documents-and-views.md)  
  
-   [ドキュメントとビューの後処理](../mfc/cleaning-up-documents-and-views.md)  
  
## <a name="see-also"></a>参照  
 [ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)

