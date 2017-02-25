---
title: "一般的なウィンドウ作成順序 | Microsoft Docs"
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
  - "フレーム ウィンドウ [C++], 作成"
  - "手順 [C++]"
  - "手順 [C++], ウィンドウの作成"
  - "ウィンドウ [C++], 作成"
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 一般的なウィンドウ作成順序
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これでウィンドウを作成する場合は、独自の子ウィンドウ、フレームワークを同じプロセス [ドキュメント\/ビューの作成](../mfc/document-view-creation.md)で説明されている実装と多く使用されます。  
  
 MFC に用意されているすべてのウィンドウ クラスは [正常な構築式](../mfc/one-stage-and-two-stage-construction-of-objects.md)が行われます。  言い換えれば、C\+\+ **new** の演算子の呼び出し時に、コンストラクターには、が、C\+\+. C\+\+ オブジェクトを初期化しましたり対応するウィンドウを作成します。  これはウィンドウ オブジェクトの [作成](../Topic/CWnd::Create.md) のメンバー関数を呼び出すことによって、そのされます。  
  
 **作成** のメンバー関数は、ウィンドウを行い、C\+\+ オブジェクトのパブリック データ メンバー [m\_hWnd](../Topic/CWnd::m_hWnd.md)で `HWND` を格納します。  **作成** は 作成パラメーター上の完全な柔軟性が得られます。  **作成**を呼び出す前に、フレームのアイコンとクラスのスタイルを設定するには、グローバル関数 [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) ウィンドウ クラスを登録することもできます。  
  
 フレーム ウィンドウの場合は、**作成**の代わりに [LoadFrame](../Topic/CFrameWnd::LoadFrame.md) メンバー関数を使用できます。  `LoadFrame` プロパティは パラメーターを使用してウィンドウを作成します。  これは、フレームのキャプション、アイコン、アクセラレータ テーブルとメニューを含むリソースから多くの既定値を取得します。  
  
> [!NOTE]
>  アイコン、アクセラレータ テーブルとメニュー リソースが共通のリソース id が、LoadFrame が読み込まれるようにするには、**IDR\_MAINFRAME**など\) である必要があります。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [ウィンドウ オブジェクト](../mfc/window-objects.md)  
  
-   [ウィンドウに、「登録は設定します」。](../mfc/registering-window-classes.md)  
  
-   [分割ウィンドウ オブジェクト](../mfc/destroying-window-objects.md)  
  
-   [ドキュメント フレーム ウィンドウの作成](../Topic/Creating%20Document%20Frame%20Windows.md)  
  
## 参照  
 [ウィンドウの作成](../Topic/Creating%20Windows.md)