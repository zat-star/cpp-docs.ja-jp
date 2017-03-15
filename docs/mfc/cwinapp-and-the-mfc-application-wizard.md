---
title: "CWinApp および MFC アプリケーション ウィザード | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWinApp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アプリケーション ウィザード [C++], および CWinApp"
  - "CWinApp クラス, および MFC アプリケーション ウィザード"
  - "MFC [C++], ウィザード"
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# CWinApp および MFC アプリケーション ウィザード
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これは、スケルトン アプリケーションを作成するときに、MFC アプリケーション ウィザードは [CWinApp](../mfc/reference/cwinapp-class.md)から派生されるアプリケーション クラスを宣言します。  MFC アプリケーション ウィザードでは、次の項目を含む実装ファイルを生成する:  
  
-   アプリケーション クラスのメッセージ マップ。  
  
-   空のクラス コンストラクター。  
  
-   クラスの一つのオブジェクトを宣言する変数。  
  
-   `InitInstance` のメンバー関数の標準の実装。  
  
 アプリケーション クラスがプロジェクト ヘッダーおよびメインのソース ファイルに格納されます。  作成するための MFC アプリケーション ウィザードで指定したプロジェクト名にクラスとファイルの名前に基づいています。  これらのクラスのコードを表示する最も簡単な方法は、[クラス ビュー](http://msdn.microsoft.com/ja-jp/8d7430a9-3e33-454c-a9e1-a85e3d2db925)です。  
  
 指定された標準実装とメッセージ マップでは、さまざまな用途に十分ですが、必要に応じて変更できます。  これらの実装で最も重要なの `InitInstance` のメンバー関数です。  通常、`InitInstance`のスケルトン実装にコードを追加します。  
  
## 参照  
 [CWinApp : アプリケーション クラス](../Topic/CWinApp:%20The%20Application%20Class.md)   
 [オーバーライド可能な CWinApp のメンバー関数](../mfc/overridable-cwinapp-member-functions.md)   
 [CWinApp のその他のサービス](../mfc/special-cwinapp-services.md)