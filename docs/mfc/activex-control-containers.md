---
title: "ActiveX コントロール コンテナー | Microsoft Docs"
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
  - "ActiveX コントロール コンテナー [C++]"
  - "OLE コントロール [C++], コンテナー"
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ActiveX コントロール コンテナー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActiveX コントロール コンテナーは完全に ActiveX コントロールをサポートし、独自のウィンドウまたはダイアログに組み込むことができるコンテナーです。  ActiveX コントロールは、多くの開発プロジェクトで使用できる再利用可能なソフトウェア要素です。  コントロールは、アプリケーションのユーザーがデータベースにアクセスできるように、データを監視し、アプリケーション内のさまざまなオプションを選択します。  ActiveX コントロールの詳細については、記事 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)を参照します。  
  
 コントロール コンテナーは、通常、プロジェクトの 2 種類の形式になります。:  
  
-   ActiveX コントロールをダイアログ ボックスのどこかで使用されるフォーム ビューなど、ダイアログ、ダイアログ形式のウィンドウ。  
  
-   ActiveX コントロールがツール バーで使用したり、別の場所でユーザーの Windows アプリケーションのウィンドウ。  
  
 ActiveX コントロール コンテナーは、公開された [メソッド](../mfc/mfc-activex-controls-methods.md) と [プロパティ](../mfc/mfc-activex-controls-properties.md)によってコントロールと対話します。  コントロール コンテナーによってアクセスおよび変更できるプロパティ ActiveX コントロール コンテナーのプロジェクトのラッパー クラスを使用して、これらのメソッドでアクセスされます。  埋め込まれたな ActiveX コントロールも発生 \(送信\) [イベント](../mfc/mfc-activex-controls-events.md) でコンテナーに操作が発生したことをコンテナーに通知するためにやり取りできます。  コントロール コンテナーはこれらの通知機能することも、または not できません。  
  
 追加記事がビルドされた ActiveX コントロール コンテナーの基本実装の問題に Visual C\+\+ で ActiveX コントロール コンテナーのプロジェクトを作成することで、複数のトピックについて説明します。:  
  
-   [MFC ActiveX コントロール コンテナーの作成](../mfc/reference/creating-an-mfc-activex-control-container.md)  
  
-   [ActiveX コントロールのコンテナー](../Topic/Containers%20for%20ActiveX%20Controls.md)  
  
-   [ActiveX コントロール コンテナー: 手動で ActiveX コントロール コンテインメントを有効にできます。](../Topic/ActiveX%20Control%20Containers:%20Manually%20Enabling%20ActiveX%20Control%20Containment.md)  
  
-   [ActiveX コントロール コンテナー: コントロール コンテナー アプリケーションにコントロールを挿入できます。](../mfc/inserting-a-control-into-a-control-container-application.md)  
  
-   [ActiveX コントロール コンテナー: メンバー変数に ActiveX コントロールを追加します。](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)  
  
-   [ActiveX コントロール コンテナー: ActiveX コントロールからのイベント処理](../mfc/activex-control-containers-handling-events-from-an-activex-control.md)  
  
-   [ActiveX コントロール コンテナー: 表示の変更、コントロール プロパティ](../mfc/activex-control-containers-viewing-and-modifying-control-properties.md)  
  
-   [ActiveX コントロール コンテナー: ActiveX コントロール コンテナーでの ActiveX コントロールのプログラミング](../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
-   [ActiveX コントロール コンテナー: 非ダイアログのコンテナー コントロールを使用する](../Topic/ActiveX%20Control%20Containers:%20Using%20Controls%20in%20a%20Non-Dialog%20Container.md)  
  
 ダイアログ ボックスに ActiveX コントロールを使用する方法の詳細については、[ダイアログ エディター](../mfc/dialog-editor.md) "を参照します。  
  
 Visual C\+\+ と MFC ActiveX コントロール クラスを使用して ActiveX コントロールを作成する方法の詳細を説明するトピックの一覧については、[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)を参照してください。  ここでは、機能ごとにグループ化されます。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)