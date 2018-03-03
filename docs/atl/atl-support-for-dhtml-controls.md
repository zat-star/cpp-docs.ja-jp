---
title: "DHTML コントロールに対する ATL のサポート |Microsoft ドキュメント"
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
- HTML controls, ATL support
- DHTML controls, ATL support
- DHTML controls
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab796752cef10c48036966c2947d711a0e385032
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atl-support-for-dhtml-controls"></a>DHTML コントロールに対する ATL のサポート
ATL を使用してダイナミック HTML (DHTML) 機能を持つコントロールを作成できます。 ATL DHTML コントロール。  
  
-   WebBrowser コントロールをホストします。  
  
-   HTML、DHTML コントロールのユーザー インターフェイス (UI) を使用して指定します。  
  
-   WebBrowser オブジェクトとそのメソッドにアクセスすると、インターフェイスを介して[IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx)です。  
  
-   C++ コードと HTML の間の通信を管理します。  
  
 DHTML コントロールは、DHTML コントロールには、追加のディスパッチ インターフェイスが含まれています。 ただし、他の ATL コントロールに似ています。 図を参照してください[DHTML コントロール プロジェクトの要素の識別](../atl/identifying-the-elements-of-the-dhtml-control-project.md)既定 DHTML プロジェクトで提供されるインターフェイスの詳細についてはします。  
  
 ATL DHTML コントロールは、Web ブラウザーまたは ActiveX コントロール テスト コンテナーなど、他のコンテナーで表示できます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [DHTML コントロール プロジェクトの要素の特定](../atl/identifying-the-elements-of-the-dhtml-control-project.md)  
 DHTML コントロール プロジェクトの要素について説明します。  
  
 [DHTML から C++ コードを呼び出す](../atl/calling-cpp-code-from-dhtml.md)  
 DHTML コントロールからの C++ コードの呼び出しの例を示します。  
  
 [ATL DHTML コントロールの作成](../atl/creating-an-atl-dhtml-control.md)  
 DHTML コントロールを作成するための手順を一覧表示します。  
  
 [ATL DHTML コントロールのテスト](../atl/testing-the-atl-dhtml-control.md)  
 ビルドおよび初期 DHTML コントロール プロジェクトをテストする方法を示します。  
  
 [ATL DHTML コントロールの変更](../atl/modifying-the-atl-dhtml-control.md)  
 コントロールに一部の機能を追加する方法を示します。  
  
 [変更後の ATL DHTML コントロールのテスト](../atl/testing-the-modified-atl-dhtml-control.md)  
 ビルドし、コントロールの追加機能をテストする方法を示します。  
  
## <a name="related-sections"></a>関連項目  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。

