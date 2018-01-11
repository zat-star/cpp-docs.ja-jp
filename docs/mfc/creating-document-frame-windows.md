---
title: "ドキュメント フレーム ウィンドウの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame windows [MFC], creating
- document templates [MFC], and document frame windows
- windows [MFC], creating
- runtime, class information
- run-time class [MFC], and document frame window creation
- document frame windows [MFC], creating
- MFC, frame windows
ms.assetid: 8671e239-b76f-4dea-afa8-7024e6e58ff5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9098026c1a38f8e60093415ba1c5a2b3678b64d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-document-frame-windows"></a>ドキュメント フレーム ウィンドウの作成
[ドキュメント/ビューの作成](../mfc/document-view-creation.md)を示していますが、どのように[CDocTemplate](../mfc/reference/cdoctemplate-class.md)オブジェクト統制フレーム ウィンドウ、ドキュメント、およびビューを作成し、それらをすべて同時に接続します。 次の 3 つ[CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)への引数、`CDocTemplate`コンス トラクターは、フレーム ウィンドウ、ドキュメント、およびファイルの新しいコマンドなどのユーザー コマンドに応答ドキュメント テンプレートを動的に作成するビュー クラスを指定します。メニューまたは MDI ウィンドウ メニューで、新しいウィンドウ コマンド。 ドキュメント テンプレートは、ビューおよびドキュメントのフレーム ウィンドウを作成するときに、後で使用するためのこの情報を格納します。  
  
 [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) 、派生は正しく動作するためのメカニズムでフレーム ウィンドウ クラスを宣言する必要があります、 [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate)マクロです。 これは、フレームワークは、フレーム ウィンドウ クラスの動的な構築メカニズムを使用してドキュメントを作成する必要があるため`CObject`です。  
  
 ドキュメントを作成するコマンドを選択すると、ドキュメント オブジェクト、そのビュー、およびビューを表示するフレーム ウィンドウを作成するドキュメント テンプレートと、フレームワークを呼び出します。 ドキュメント テンプレートが、適切なクラスのオブジェクトを作成して、ドキュメント フレーム ウィンドウの作成時から派生したクラス[CFrameWnd](../mfc/reference/cframewnd-class.md) SDI アプリケーションまたはから[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) MDI のアプリケーション。 フレームワークのフレーム ウィンドウ オブジェクトの[LoadFrame](../mfc/reference/cframewnd-class.md#loadframe)メンバー関数をリソースから作成情報を取得し、Windows ウィンドウを作成します。 フレームワークは、ウィンドウ ハンドルをフレーム ウィンドウ オブジェクトにアタッチします。 ドキュメント フレーム ウィンドウの子ウィンドウとして、ビューを作成します。  
  
 決定するときに注意してください[初期化のタイミング](../mfc/when-to-initialize-cwnd-objects.md)、 `CWnd`-派生オブジェクト。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [CObject (動的な作成メカニズムはその) からクラスを派生します。](../mfc/deriving-a-class-from-cobject.md)  
  
-   [ドキュメント/ビューの作成 (テンプレートおよびフレーム ウィンドウの作成)](../mfc/document-view-creation.md)  
  
-   [フレーム ウィンドウの破棄](../mfc/destroying-frame-windows.md)  
  
## <a name="see-also"></a>参照  
 [フレーム ウィンドウの使用](../mfc/using-frame-windows.md)

