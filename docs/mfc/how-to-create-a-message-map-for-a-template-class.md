---
title: "方法 : テンプレート クラスのメッセージ マップを作成する | Microsoft Docs"
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
  - "メッセージ マップ, テンプレート クラス"
  - "テンプレート クラス, 作成 (メッセージ マップを)"
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 方法 : テンプレート クラスのメッセージ マップを作成する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC メッセージ マップは適切な C\+\+ オブジェクト インスタンスに Windows メッセージを指示するための効率的な方法を提供します。  MFC メッセージ マップ対象の例はアプリケーション クラス、ドキュメント、ビュー クラスのコントロール クラスが、などがあります。  
  
 従来の MFC メッセージ マップでは [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) マクロを使用してメッセージ マップの開始要素、各メッセージ処理クラス メソッドのマクロ エントリ、最後に [END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md) マクロを宣言するとメッセージ マップの終了位置を宣言することを宣言します。  
  
 [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) マクロの 1 種類の制約を含むクラス テンプレート引数とともに使用された場合に発生します。  テンプレート クラスを使用すると、このマクロは、マクロの展開時にそのテンプレート パラメーターによってコンパイル時のエラーが発生します。  [BEGIN\_TEMPLATE\_MESSAGE\_MAP](../Topic/BEGIN_TEMPLATE_MESSAGE_MAP.md) マクロは独自のメッセージ マップを宣言するための単一のテンプレート引数を含むクラスを使用できるように設計されています。  
  
## 例  
 外部データ ソースの同期を実現するため [CListBox](../Topic/CListBox%20Class.md) MFC クラスを拡張する例を示します。  **CSyncListBox** Dinner Now クラスは次のように宣言されます。:  
  
 [!code-cpp[NVC_MFC_CListBox#42](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_1.h)]  
  
 **CSyncListBox** クラスと同期するデータ ソースを表す単一の型に template 宣言されたです。  また、クラスのメッセージ マップに参加する 3 種類のメソッドを宣言します: **OnPaint**、**OnDestroy**と **OnSynchronize**。  **OnSynchronize** のメソッドは次のように実装されます:  
  
 [!code-cpp[NVC_MFC_CListBox#43](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_2.cpp)]  
  
 上記の実装は **CSyncListBox** クラスが **GetCount** のメソッドを、**CArray**など、**CList**実装する、**CMap**、任意のクラス型に特化されるようにします。  **StringizeElement** 関数は次によってとテンプレート関数です:  
  
 [!code-cpp[NVC_MFC_CListBox#44](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_3.cpp)]  
  
 通常、このクラスのメッセージ マップは次のように定義されています:  
  
 `BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)`  
  
 `ON_WM_PAINT()`  
  
 `ON_WM_DESTROY()`  
  
 `ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)`  
  
 `END_MESSAGE_MAP()`  
  
 **LBN\_SYNCHRONIZE** がアプリケーションで定義したカスタム ユーザー定義メッセージです。など:  
  
 [!code-cpp[NVC_MFC_CListBox#45](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_4.cpp)]  
  
 上のマップ マクロは、**CSyncListBox** クラスのテンプレートの仕様は、マクロの展開時に指定されていることが原因でコンパイルされません。  **BEGIN\_TEMPLATE\_MESSAGE\_MAP** マクロは展開されたマクロ マップに指定されたテンプレート パラメーターを組み込むことによって、これを解決します。  このクラスのメッセージ マップがあります:  
  
 [!code-cpp[NVC_MFC_CListBox#46](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_5.cpp)]  
  
 次に **CStringList** オブジェクトを使用して **CSyncListBox** クラスのサンプル:使用されています。  
  
 [!code-cpp[NVC_MFC_CListBox#47](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_6.cpp)]  
  
 テストを実行するには、**StringizeElement** 関数は **CStringList** クラスを使用するように特化する必要があります:  
  
 [!code-cpp[NVC_MFC_CListBox#48](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_7.cpp)]  
  
## 参照  
 [BEGIN\_TEMPLATE\_MESSAGE\_MAP](../Topic/BEGIN_TEMPLATE_MESSAGE_MAP.md)   
 [メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)