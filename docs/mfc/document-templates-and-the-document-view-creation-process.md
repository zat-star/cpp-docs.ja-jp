---
title: "ドキュメント テンプレートとドキュメント/ビューの作成手順 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocTemplate クラス"
  - "ドキュメント テンプレート, およびビュー"
  - "ドキュメント/ビュー アーキテクチャ, 作成 (ドキュメント/ビューを)"
  - "アイコン, 複数のドキュメント テンプレートの"
  - "MFC, ドキュメント テンプレート"
  - "複数のドキュメント テンプレート"
  - "1 つのドキュメント テンプレート"
  - "テンプレート, ドキュメント テンプレート"
ms.assetid: 311ce4cd-fbdf-4ea1-a51b-5bb043abbcee
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ドキュメント テンプレートとドキュメント/ビューの作成手順
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関連ビューおよびフレーム ウィンドウでドキュメントを作成する複雑なプロセスを管理するには、2 種類のドキュメント テンプレート クラスを使用して T: SDI アプリケーションの [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) と MDI アプリケーションの [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)。  `CSingleDocTemplate` は 1 個の型に 1 個のドキュメントを同時に作成し、保存できます。  `CMultiDocTemplate` は 1 種類の多くの開いているドキュメントのリストを保持します。  
  
 アプリケーションは複数のドキュメントの種類。  たとえば、アプリケーションでテキスト ドキュメントとグラフィック ドキュメントをサポートする場合があります。  このようなアプリケーションでは、ユーザーがファイル メニューの新規作成コマンドを選択すると、使用できる新しいドキュメント リストを開くを選択するダイアログ ボックスを表示します。  サポートされている各ドキュメント型の場合、アプリケーションでは、個別のドキュメント テンプレート オブジェクトを使用します。  次の図は、サポートが 2 のドキュメント型など、開いているドキュメントに示す MDI アプリケーションの構成について説明します。  
  
 ![2 ドキュメント タイプを持つ MDI アプリケーション](../mfc/media/vc387h1.gif "vc387H1")  
2 つのドキュメント タイプをサポートする MDI アプリケーション  
  
 ドキュメント テンプレートは、アプリケーション オブジェクトによって作成および保持されます。  アプリケーションの `InitInstance` 関数の中に実行する主な五つのタスクの 1 つが、適切な種類の一つ以上のドキュメント テンプレートを作成することです。  この機能は [ドキュメント テンプレートの作成](../Topic/Document%20Template%20Creation.md)で説明します。  Application オブジェクトは、テンプレートの一覧で、各ドキュメント テンプレートへのポインターを格納し、ドキュメント テンプレートを追加するためのインターフェイスを提供します。  
  
 複数の種類のドキュメントをサポートする必要がある [AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md) に各ドキュメントの種類の追加の呼び出しを追加する必要があります。  
  
 アイコンは、アプリケーションのドキュメント テンプレートの位置に基づいて各ドキュメント テンプレートに登録されます。  ドキュメント テンプレートの順序は、`AddDocTemplate`と追加されたときの順序によって決まります。  MFC は、アプリケーションの最初のアイコン リソースをアプリケーション アイコンであると次のアイコン リソースで最初にドキュメント アイコンなどとします。  
  
 たとえば、ドキュメント テンプレートには、アプリケーション用の 3 番目のチュートリアルです。  アプリケーションにアイコン リソース インデックスが 3 である場合、そのアイコンは、ドキュメント テンプレートに使用されます。  アイコンは、既定としてインデックス 0 以外では使用されます。  
  
## 参照  
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)   
 [ドキュメント テンプレートの作成](../Topic/Document%20Template%20Creation.md)   
 [ドキュメントおよびビューの作成](../mfc/document-view-creation.md)   
 [各種 MFC オブジェクト間の関係](../mfc/relationships-among-mfc-objects.md)   
 [新しいドキュメント、ウィンドウ、ビューの作成](../Topic/Creating%20New%20Documents,%20Windows,%20and%20Views.md)