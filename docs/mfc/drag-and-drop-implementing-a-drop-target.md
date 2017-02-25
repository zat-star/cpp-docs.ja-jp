---
title: "ドラッグ アンド ドロップ : ドロップ ターゲットの実装 | Microsoft Docs"
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
  - "ドラッグ アンド ドロップ, ドロップ ターゲット"
  - "OLE のドラッグ アンド ドロップ, ドロップ ターゲット"
  - "OLE のドラッグ アンド ドロップ, 実装 (ドロップ ターゲットを)"
ms.assetid: 0689f1ec-5326-4008-b226-4b373c881358
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ドラッグ アンド ドロップ : ドロップ ターゲットの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この記事のアウトライン アプリケーションにドロップ ターゲットを行う方法を示します。  ドロップ ターゲットを実装すると、受け取り、がドロップ ソースを実装しますが、より多くの作業を、比較的簡単です。  これらの手法は、非 OLE アプリケーションに適用されます。  
  
#### ドロップ ターゲットを実装するには  
  
1.  ドロップ ターゲットで、対象となるアプリケーションの各ビューにメンバー変数を追加します。  このメンバー変数は、アセンブリから型 `COleDropTarget` または派生クラスである必要があります。  
  
2.  `WM_CREATE` メッセージ \(通常 `OnCreate`\) を処理するビュー クラスの関数から、新しいメンバー変数の `Register` メンバー関数を呼び出します。  `Revoke` は、をビューが破棄されるときに自動的に呼び出されます。  
  
3.  次の関数をオーバーライドします。  アプリケーション全体の動作が必要な場合は、ビュー クラスの関数をオーバーライドします。  動作を複数の図における変更または`CView` の Windows 以外の低下を有効にする必要がある場合は、これらの関数の `COleDropTarget`\-派生クラスをオーバーライドします。  
  
    |オーバーライド|割り当てるには|  
    |-------------|-------------|  
    |`OnDragEnter`|ウィンドウで発生したドロップ操作。  カーソルが最初にウィンドウを入力するときに呼び出されます。|  
    |`OnDragLeave`|ドラッグ操作が指定されたウィンドウの外に出ると、特別な動作。|  
    |`OnDragOver`|ウィンドウで発生したドロップ操作。  カーソルがウィンドウにドラッグされたときに呼び出されます。|  
    |`OnDrop`|指定されたウィンドウにドロップするデータの処理。|  
    |`OnScrollBy`|スクロールがターゲット ウィンドウで必要なときに特別な動作の。|  
  
 これらの関数は連携する方法の例については、" MFC サンプルの OLE [OCLIENT](../top/visual-cpp-samples.md) の一部である MAINVIEW.CPP ファイルを参照してください。  
  
 詳細については、次のトピックを参照してください。  
  
-   [ドラッグ ソースの実装](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [作成と破棄の OLE データ オブジェクトとデータ ソース](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [処理の OLE データ オブジェクトとデータ ソース](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## 参照  
 [ドラッグ アンド ドロップ \(OLE\)](../mfc/drag-and-drop-ole.md)   
 [COleDropTarget クラス](../Topic/COleDropTarget%20Class.md)