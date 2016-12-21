---
title: "ウィンドウ オブジェクト | Microsoft Docs"
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
  - "フレーム ウィンドウ [C++], C++ ウィンドウ オブジェクト"
  - "HWND"
  - "HWND, ウィンドウ オブジェクト"
  - "メッセージ [C++], Windows"
  - "MFC [C++], ウィンドウ"
  - "オブジェクト [C++], ウィンドウ"
  - "Visual C++, ウィンドウ オブジェクト"
  - "ウィンドウ メッセージ [C++]"
  - "ウィンドウ オブジェクト [C++]"
  - "ウィンドウ [C++], C++ ウィンドウ オブジェクト"
  - "Windows のウィンドウ [C++]"
ms.assetid: 28b33ce2-af05-4617-9d03-1cb9a02be687
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ウィンドウ オブジェクト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC は、ウィンドウの `HWND` ハンドルをカプセル化するクラス [CWnd](../Topic/CWnd%20Class.md) を指定します。  `CWnd` オブジェクトは `HWND` から別のウィンドウを、それを含むことを表す C \+\+.ウィンドウ オブジェクトです。  独自の子ウィンドウ クラスを派生するために `CWnd` を使用するか、`CWnd`から派生される多くの MFC クラスの 1 を使用します。  クラス `CWnd` はツール バーなど、フレーム ウィンドウ、ダイアログ ボックス、子ウィンドウ、コントロールとコントロール バーを含むすべてのウィンドウの基本クラスです。  [C \+\+.ウィンドウ HWND オブジェクトとの関係](../Topic/Relationship%20Between%20a%20C++%20Window%20Object%20and%20an%20HWND.md) に精通している場合は、MFC で有効なプログラミングにとって重要です。  
  
 MFC は、ウィンドウの既定の機能と管理を提供します `CWnd` から独自のクラスを派生し、提供された機能をカスタマイズするには、メンバー関数を使用できます。  `CWnd` オブジェクトを構築し、[作成](../Topic/CWnd::Create.md) のメンバー関数を呼び出して、子ウィンドウを作成し、`CWnd` メンバー関数を使用して子ウィンドウをカスタマイズします。  フレーム ウィンドウに [CView](../Topic/CView%20Class.md)から、フォーム ビューまたはツリー ビューなどの派生されるオブジェクトを埋め込むことができます。  と分割ペインの [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)クラスによって提供されるドキュメントの複数のビューをサポートできます。  
  
 クラス `CWnd` の各オブジェクトの派生には、独自のハンドラーに Windows メッセージまたはコマンド ID をマップできるメッセージ マップが含まれます。  
  
 Windows のプログラミングの一般的な文献で、習得に適したリソース `HWND` API をカプセル化する `CWnd` メンバー関数を使用する方法を示します。  
  
## CWnd のアクティブ化の関数  
 `CWnd` と [派生クラスのウィンドウ](../Topic/Derived%20Window%20Classes.md) コンストラクターは、オブジェクトを初期化するために、デストラクターとメンバー関数を使用する基になる Windows 構造体を作成し、カプセル化された `HWND`にアクセスします。  `CWnd` は メッセージをカプセル化するメンバー関数を提供し、ウィンドウの状態にアクセスして送信するための Windows API は、座標を変換し、更新し、スクロールし、クリップボードなどのさまざまなタスクにアクセスします。  `HWND` 引数を受け取るほとんどの Windows のウィンドウ管理 API は `CWnd`のメンバー関数としてカプセル化されます。  関数やパラメーターの名前は `CWnd` のメンバー関数に保持されます。  `CWnd`でカプセル化されている Windows API については [CWnd](../Topic/CWnd%20Class.md)クラスを参照してください。  
  
## CWnd および Windows メッセージ  
 `CWnd` の主な目的の 1 つが `WM_PAINT` または `WM_MOUSEMOVE`など、Windows メッセージを処理するためのインターフェイスを提供します。  `CWnd` のメンバー関数の多くは、標準のメッセージ **afx\_msg** — Identity と `OnPaint` と **OnMouseMove**などのプレフィックスにはこれらのハンドラー「」、になっています。  詳細 について[メッセージの処理とマップ](../mfc/message-handling-and-mapping.md) のおよびメッセージ処理。  多くの情報は、特殊な目的のために自分で作成したウィンドウおよびフレームワークのウィンドウにも同じように適用されます。  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [C \+\+.ウィンドウ HWND オブジェクトとの関係](../Topic/Relationship%20Between%20a%20C++%20Window%20Object%20and%20an%20HWND.md)  
  
-   [派生クラスのウィンドウ](../Topic/Derived%20Window%20Classes.md)  
  
-   [ウィンドウの作成](../Topic/Creating%20Windows.md)  
  
-   [分割ウィンドウ オブジェクト](../mfc/destroying-window-objects.md)  
  
-   [HWND から CWnd をデタッチする](../Topic/Detaching%20a%20CWnd%20from%20Its%20HWND.md)  
  
-   [ウィンドウ オブジェクトの使用](../Topic/Working%20with%20Window%20Objects.md)  
  
-   [デバイス コンテキスト](../Topic/Device%20Contexts.md): Windows の描画をデバイス非依存オブジェクトの作成  
  
-   [グラフィック オブジェクト](../mfc/graphic-objects.md): ペン、ブラシ、フォント、ビットマップ、パレット、領域  
  
## 参照  
 [Windows](../mfc/windows.md)