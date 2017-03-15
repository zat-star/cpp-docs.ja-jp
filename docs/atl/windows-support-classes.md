---
title: "ウィンドウ サポート クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.windows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, ウィンドウ"
  - "ウィンドウ [C++], ATL"
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ウィンドウ サポート クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のクラスはウィンドウをサポートします:  
  
-   [\_U\_MENUorID](../atl/reference/u-menuorid-class.md) は **CreateWindow** と **CreateWindowEx**のラッパーを提供します。  
  
-   [CWindow](../atl/reference/cwindow-class.md) は、ウィンドウを操作するためのメソッドが含まれています。  `CWindow` は、`CWindowImpl`、`CDialogImpl`、および `CContainedWindow` の基本クラスです。  
  
-   [CWindowImpl](../Topic/CWindowImpl%20Class.md) は新しいウィンドウ クラスに基づいてウィンドウを実装します。  また、サブクラスまたはウィンドウにスーパークラス化できます。  
  
-   [CDialogImpl](../Topic/CDialogImpl%20Class.md) は、ダイアログ ボックスを実装します。  
  
-   [CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md) は、ダイアログ ボックス \(モーダルまたはモードレス\) ホストの ActiveX コントロール実装します。  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) は、基本的な機能のダイアログ ボックス \(モーダルまたはモードレス\) 実装します。  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) は、ActiveX コントロールをホストするウィンドウを操作します。  
  
-   [CAxWindow2T](../Topic/CAxWindow2T%20Class.md) は、ActiveX コントロールおよびライセンスされた ActiveX コントロールをホストするためのサポートを持つウィンドウを操作するためのメソッドを提供します。  
  
-   [CContainedWindowT](../Topic/CContainedWindowT%20Class.md) は別のオブジェクトに含まれているウィンドウを実装します。  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) は新しいウィンドウ クラス情報を管理します。  
  
-   メッセージ マップの[CDynamicChain](../atl/reference/cdynamicchain-class.md) の サポートの動的チェイン。  
  
-   [CMessageMap](../atl/reference/cmessagemap-class.md) は、オブジェクトが他のオブジェクトにメッセージ マップを公開するようにします。  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) は、ATL ウィンドウ オブジェクトの特性を標準化する簡単な方法を提供します。  
  
-   [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) はウィンドウの作成に使用されるウィンドウ スタイルと拡張スタイルに既定値を指定します。  これらの値はウィンドウの作成時に指定された値に、論理 OR 演算子を使用して、に追加されます。  
  
## 関連トピック  
 [ATL ウィンドウ クラス](../Topic/ATL%20Window%20Classes.md)  
  
 [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)  
  
## 参照  
 [クラスの概要](../atl/atl-class-overview.md)   
 [メッセージ マップ マクロ](../atl/reference/message-map-macros-atl.md)   
 [ウィンドウ クラスに関するマクロ](../atl/reference/window-class-macros.md)