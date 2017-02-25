---
title: "MFC アプリケーション アーキテクチャ クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アプケーション アーキテクチャ クラス"
  - "クラス [C++], MFC"
  - "MFC [C++], アプリケーション開発"
  - "MFC [C++], クラス"
ms.assetid: 71b2de54-b44d-407e-9c71-9baf954e18d9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# MFC アプリケーション アーキテクチャ クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このカテゴリのクラスは、.NET Framework アプリケーションのアーキテクチャを提供します。  これらは、ほとんどのアプリケーションに共通の機能を提供します。  アプリケーション固有の機能を追加するために、フレームワークが設定されます。  通常は、新しいクラスをアーキテクチャ クラスから派生し、新しいメンバーを追加するか、既存のメンバー関数をオーバーライドすることで実現します。  
  
 [アプリケーション ウィザード](../Topic/MFC%20Application%20Wizard.md) は さまざまな方法でアプリケーション フレームワークを使用するアプリケーションの型が生成されます。  SDI \(シングル ドキュメント インターフェイス\)、マルチ ドキュメント インターフェイス \(MDI\) アプリケーションでは、ドキュメント\/ビュー アーキテクチャというフレームワークの一部を活用します。  アプリケーションの他の型は、ダイアログ ベースのアプリケーションなど、フォーム ベースのアプリケーションと DLL、ドキュメント\/ビュー アーキテクチャ機能の一部だけを使用します。  
  
 ドキュメント\/ビュー アプリケーション、ドキュメント、ビュー、およびフレーム ウィンドウの一つ以上のセットが含まれます。  ドキュメントテンプレート オブジェクトでは、各ドキュメント\/ビュー、フレーム セットのクラスを関連付けます。  
  
 MFC アプリケーションでは、ドキュメント\/ビュー アーキテクチャを使用する必要はありませんが、それにいくつかの利点があります。  MFC OLE コンテナーとサーバー サポートは、ドキュメント\/ビュー アーキテクチャの印刷や印刷プレビューのサポートになるように基づきます。  
  
 すべての MFC アプリケーションに 2 個以上のオブジェクトがあります: [CWinApp](../mfc/reference/cwinapp-class.md)から、種類のメイン ウィンドウ オブジェクト派生される、アプリケーション オブジェクト [CWnd](../Topic/CWnd%20Class.md)から派生 \(通常は間接的になります。\(通常は、メイン ウィンドウが `CWnd`から派生される [CFrameWnd](../mfc/reference/cframewnd-class.md)、[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)、または [CDialog](../mfc/reference/cdialog-class.md)から派生されます\)。  
  
 ドキュメント\/ビュー アーキテクチャを使用するアプリケーションは追加オブジェクトが含まれます。  プリンシパル オブジェクトは、次の操作:  
  
-   クラス [CWinApp](../mfc/reference/cwinapp-class.md)から派生されるアプリケーション オブジェクトで説明したようにします。  
  
-   クラス [CDocument](../Topic/CDocument%20Class.md)から派生される一つ以上のドキュメント クラス オブジェクト。  ドキュメント クラスのオブジェクトは、ビューで処理されるデータを内部表現を行います。  これらは、データ ファイルに関連付けられている可能性があります。  
  
-   クラス [CView](../Topic/CView%20Class.md)から派生される一つ以上のビュー オブジェクト。  各ビューは、ドキュメントに関連付けられ、フレーム ウィンドウに関連付けられたウィンドウです。  ビューはドキュメント クラスのオブジェクトに格納されているデータを表示および処理します。  
  
 ドキュメント\/ビュー アプリケーションは、フレーム ウィンドウ \([CFrameWnd](../mfc/reference/cframewnd-class.md)から派生される\) とドキュメント テンプレートを含む \([CDocTemplate](../mfc/reference/cdoctemplate-class.md)から派生される\)。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)