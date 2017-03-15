---
title: "Active ドキュメント コンテナー アプリケーションの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Active ドキュメント コンテナー [C++], 作成"
  - "アクティブ ドキュメント [C++], コンテナー"
  - "アプリケーション [MFC], Active ドキュメント コンテナー"
  - "コンテナー [C++], アクティブ ドキュメント"
  - "MFC COM [C++], Active ドキュメント コンテインメント"
ms.assetid: 14e2d022-a6c5-4249-8712-706b0f4433f7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Active ドキュメント コンテナー アプリケーションの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ためのおよびほとんどの方法は、アクティブ ドキュメント コンテナー アプリケーションを作成し、MFC アプリケーション ウィザードを使用して MFC EXE のコンテナー アプリケーションを作成することと、アクティブ ドキュメントのコンテインメントをサポートするようにアプリケーションを変更します。  
  
#### Active ドキュメント コンテナー アプリケーションを作成するには  
  
1.  **\[ファイル\]** メニューから、**\[新規作成\]** のサブメニューから **\[プロジェクト\]** をクリックします。  
  
2.  左ペインで、プロジェクトの種類を **\[Visual C\+\+\]** をクリックします。  
  
3.  右ペインで **\[MFC アプリケーション\]** を選択します。  
  
4.  プロジェクト `MyProj`を付けます。、**\[OK\]** をクリックします。  
  
5.  **\[複合ドキュメント サポート\]** ページを選択します。  
  
6.  **\[コンテナー\]** または **\[コンテナー\/フル サーバー\]** オプションを選択します。  
  
7.  **\[Active ドキュメント コンテナー\(D\)\]** チェック ボックスをオンにします。  
  
8.  \[完了\] をクリックします。  
  
9. MFC アプリケーション ウィザードのアプリケーションを生成する作業が終了したら、ソリューション エクスプローラーを使用すると、次のファイルを開く:  
  
    -   MyProjview.cpp  
  
10. MyProjview.cpp では、次の変更を行います。:  
  
    -   `CMyProjView::OnPreparePrinting`では、次のコードでは、関数の内容を置換する:  
  
         [!code-cpp[NVC_MFCDocView#56](../mfc/codesnippet/CPP/creating-an-active-document-container-application_1.cpp)]  
  
     `OnPreparePrinting` は 印刷サポートを提供します。  既定の状態であるこのコードは `DoPreparePrinting`を置き換えます。  
  
     Active ドキュメント コンテインメントが強化された印刷スキームを提供し、T:  
  
    -   `IPrint` インターフェイスを通じて初めて呼び出すアクティブ ドキュメントをそれ自身を出力するように指定することもできます。  これは、コンテナーがプリンターの `CDC`オブジェクトに含まれる項目のイメージをする必要があります。前の OLE コンテインメントとは異なります。  
  
    -   エラーが発生した場合は、含まれる項目を `IOleCommandTarget`インターフェイスを通じて自身を印刷する方法を説明します。  
  
    -   エラーが発生した場合は、項目の独自の描画を実行します。  
  
     前のコードで実装されるように静的メンバー関数 `COleDocObjectItem::OnPrint` と `COleDocObjectItem::OnPreparePrinting`は、この強化された印刷スキームを処理します。  
  
11. 独自の実装を追加し、アプリケーションをビルドします。  
  
## 参照  
 [Active ドキュメント コンテインメント](../mfc/active-document-containment.md)