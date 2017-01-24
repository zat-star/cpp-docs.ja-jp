---
title: "ATL ウィンドウ クラスの概要 | Microsoft Docs"
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
  - "ウィンドウ クラス"
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL ウィンドウ クラスの概要
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の ATL ウィンドウ クラスはを実装し、処理するように設計されています:  
  
-   [CWindow](../atl/reference/cwindow-class.md) は `CWindow` の Windows ハンドルをオブジェクトにアタッチすることができます。  次に、ウィンドウを操作するための `CWindow` のメソッドを呼び出します。  
  
-   [CWindowImpl](../Topic/CWindowImpl%20Class.md) では、メッセージ マップを含む新しいウィンドウとプロセス メッセージを実装できるようにします。  既存のウィンドウ新しいウィンドウ クラス、スーパークラス既存のクラス、またはサブクラスに基づいてウィンドウを作成できます。  
  
-   [CDialogImpl](../Topic/CDialogImpl%20Class.md) では、メッセージ マップを持つモーダルまたはモードレス ダイアログ ボックスとプロセスのメッセージを実装できるようにします。  
  
-   [CContainedWindowT](../Topic/CContainedWindowT%20Class.md) は、メッセージ マップに別のクラスに含まれているペインを実行するビルド済みのクラスです。  `CContainedWindowT` を使用して 1 個のクラスで処理するメッセージを集中化することができます。  
  
-   ActiveX コントロールのホスト[CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md) は、ダイアログ ボックス \(モーダルまたはモードレス\) 実装できるようにします。  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) は、基本的な機能のモーダル ダイアログ ボックスを実装できるようにします。  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) は、ActiveX コントロールをホストするウィンドウを実装できるようにします。  
  
-   [CAxWindow2T](../Topic/CAxWindow2T%20Class.md) は、ライセンスされた ActiveX コントロールをホストするウィンドウを実装できるようにします。  
  
 特定のウィンドウ クラスに加えて、ATL は ATL ウィンドウ オブジェクトの実装を簡単にするために設計された複数のクラスを提供します。  それらは次のとおりです。  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) は新しいウィンドウ クラス情報を管理します。  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) と [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) は、ATL ウィンドウ オブジェクトの特性を標準化する簡単な方法を提供します。  
  
## 参照  
 [ウィンドウ クラス](../Topic/ATL%20Window%20Classes.md)