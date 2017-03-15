---
title: "DHTML コントロールに対する ATL のサポート | Microsoft Docs"
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
  - "DHTML コントロール"
  - "DHTML コントロール, ATL サポート"
  - "HTML コントロール, ATL サポート"
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# DHTML コントロールに対する ATL のサポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL を使用して、ダイナミック HTML \(DHTML\) 機能のコントロールを作成できます。  ATL DHTML コントロール:  
  
-   WebBrowser コントロールをホストします。  
  
-   HTML、を使用して、DHTML コントロールのユーザー インターフェイス \(UI\) を指定します。  
  
-   インターフェイス、[IWebBrowser2](https://msdn.microsoft.com/en-us/library/aa752127.aspx)を使用して Web ブラウザーのオブジェクトおよびメソッドにアクセスします。  
  
-   C\+\+ コードと HTML の間の通信管理。  
  
 DHTML コントロールは、DHTML コントロールで追加のディスパッチ インターフェイスを含む以外、他の ATL コントロールにも似ています。  Project Server に既定の DHTML で提供されるインターフェイスの図については [DHTML コントロールのプロジェクト要素の識別](../atl/identifying-the-elements-of-the-dhtml-control-project.md) の図を参照してください。  
  
 ActiveX コントロール テスト コンテナーなどの Web ブラウザーなどのコンテナーの ATL DHTML コントロールを表示できます。  
  
## このセクションの内容  
 [DHTML コントロールのプロジェクト要素の識別](../atl/identifying-the-elements-of-the-dhtml-control-project.md)  
 DHTML コントロールのプロジェクト要素について説明します。  
  
 [DHTML から C\+\+ コードの呼び出し](../Topic/Calling%20C++%20Code%20from%20DHTML.md)  
 DHTML コントロールから C\+\+ コードを呼び出す例を示します。  
  
 [ATL DHTML コントロールの作成](../atl/creating-an-atl-dhtml-control.md)  
 DHTML コントロールを作成するための手順を示します。  
  
 [ATL DHTML コントロールのテスト](../atl/testing-the-atl-dhtml-control.md)  
 最初の DHTML コントロールのテスト プロジェクトをビルドする方法を示します。  
  
 [ATL DHTML コントロールの変更](../atl/modifying-the-atl-dhtml-control.md)  
 コントロールに機能を追加する方法を示します。  
  
 [された ATL DHTML コントロールのテスト](../atl/testing-the-modified-atl-dhtml-control.md)  
 コントロールの追加機能をビルドをテストする方法を説明します。  
  
## 関連項目  
 [&#91;ATL&#93;](../atl/active-template-library-atl-concepts.md)  
 Active Template Library を使用したプログラミングの概念を説明するトピックへのリンクを示します。