---
title: "Active ドキュメント コンテナー アプリケーションの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- active document containers [MFC], creating
- MFC COM, active document containment
- applications [MFC], active document container
ms.assetid: 14e2d022-a6c5-4249-8712-706b0f4433f7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 077d15837ed857ac983c3c9f9d4e7853b45aeee5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-active-document-container-application"></a>Active ドキュメント コンテナー アプリケーションの作成
Active ドキュメント コンテナー アプリケーションを作成する最も簡単な最も推奨される方法は MFC アプリケーション ウィザードを使用して MFC EXE コンテナー アプリケーションを作成し、active ドキュメント コンテインメントをサポートするためにアプリケーションを変更します。  
  
#### <a name="to-create-an-active-document-container-application"></a>Active ドキュメント コンテナー アプリケーションを作成するには  
  
1.  **ファイル** メニューをクリックして**プロジェクト**から、**新規**サブメニュー。  
  
2.  左側のウィンドウからをクリックして**Visual C**プロジェクトの種類。  
  
3.  選択**MFC アプリケーション**右側のウィンドウからです。  
  
4.  プロジェクトに名前を`MyProj`をクリックして**OK**です。  
  
5.  選択、**複合ドキュメント サポート**ページ。  
  
6.  選択、**コンテナー**または**コンテナー/フル サーバー**オプション。  
  
7.  選択、 **Active ドキュメント コンテナー**チェック ボックスをオンします。  
  
8.  **[完了]**をクリックします。  
  
9. MFC アプリケーション ウィザードでは、アプリケーションの生成が完了すると、ソリューション エクスプ ローラーを使用して、次のファイルを開きます。  
  
    -   MyProjview.cpp  
  
10. MyProjview.cpp では、次の変更を行います。  
  
    -   `CMyProjView::OnPreparePrinting`関数の内容を次のコードに置き換えます。  
  
         [!code-cpp[NVC_MFCDocView#56](../mfc/codesnippet/cpp/creating-an-active-document-container-application_1.cpp)]  
  
     `OnPreparePrinting`印刷のサポートを提供します。 このコードを置き換えます`DoPreparePrinting`、これは既定の印刷準備します。  
  
     Active ドキュメント コンテインメントには、印刷スキームの強化が提供します。  
  
    -   使用してアクティブなドキュメントを最初に呼び出すことができます、`IPrint`インターフェイスし、それ自体を印刷するように指定します。 これに対し、プリンターに含まれているアイテムのイメージを表示するために、コンテナーがされました、以前の OLE コンテインメント`CDC`オブジェクト。  
  
    -   失敗した場合、通知に含まれるアイテムをそれ自体を印刷するその`IOleCommandTarget`インターフェイス  
  
    -   失敗した場合は、独自のアイテムの表示を確認します。  
  
     静的メンバー関数は、`COleDocObjectItem::OnPrint`と`COleDocObjectItem::OnPreparePrinting`前のコードに実装されると、この印刷スキームの強化を処理します。  
  
11. 独自の実装を追加し、アプリケーションをビルドします。  
  
## <a name="see-also"></a>参照  
 [Active ドキュメント コンテインメント](../mfc/active-document-containment.md)

