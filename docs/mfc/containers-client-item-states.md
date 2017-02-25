---
title: "コンテナー : クライアント アイテムの状態 | Microsoft Docs"
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
  - "クライアント アイテムと OLE コンテナー"
  - "有効期間, 有効期間の状態と OLE コンテナーのクライアント アイテム"
  - "OLE コンテナー, クライアント アイテムの状態"
  - "状態, OLE コンテナー クライアント アイテム"
ms.assetid: e7021caa-bd07-4adb-976e-f5f3d025bc53
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# コンテナー : クライアント アイテムの状態
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、その有効期間中にさまざまな状態をクライアント項目のパスについて説明します。  
  
 クライアント項目は複数の状態を作成し、アクティブ化、変更、および保存するときに適用されます。  項目の状態が変更されるたびに、フレームワークは `OLE_CHANGED_STATE` 通知の [COleClientItem::OnChange](../Topic/COleClientItem::OnChange.md) を呼び出します。  2 番目のパラメーターは **COleClientItem::ItemState** の列挙体の値です。  これは、次のいずれかの:  
  
-   **COleClientItem::emptyState**  
  
-   **COleClientItem::loadedState**  
  
-   **COleClientItem::openState**  
  
-   **COleClientItem::activeState**  
  
-   **COleClientItem::activeUIState**  
  
 空の状態で、クライアント項目も完全に項目ではありません。  メモリに対してに割り当てられたが、OLE アイテムのデータがまだ初期化されていません。  これは **new** への呼び出しで作成されたが、ある、一般的な、ステップを作成する 2 番目の手順が発生しない場合にクライアント項目は状態です。  
  
 `COleClientItem::CreateFromFile` または **CreateFrom**別の*その* 関数の呼び出しによって実行される 2 番目の手順では、項目は完全に作成されます。  OLE データは `COleClientItem`\-派生オブジェクト \(クリップボードなどのファイルやそのほかのソースから、\) に関連付けられています。  項目は読み込み済み状態に次にあります。  
  
 項目はコンテナーのドキュメントを開くのではなく、サーバーのウィンドウで開いた場合は、開いている \(または完全に開きます\) 状態になります。  この状態で項目が他の場所でアクティブであることを示すために、あや表示陰影は通常、コンテナー ウィンドウの項目の表現に描画されます。  
  
 項目はアクティブ化された場合、アクティブ状態は、通常、簡単にのみ適用されます。  その後、サーバーがコンテナーのものとメニューやツール バーなどのユーザー インターフェイス コンポーネントをマージした UI アクティブ状態になります。  これらのユーザー インターフェイス コンポーネントの有無はアクティブ状態と UI のアクティブ状態を区別します。  それ以外の場合は、アクティブ状態は、UI の状態がアクティブになります。  読み込まれるか、開いている状態に達するまで OLE アイテムの元の状態情報を保持するためにサーバー サポートに戻す、サーバーが必要な場合。  
  
## 参照  
 [コンテナー](../mfc/containers.md)   
 [アクティベーション](../mfc/activation-cpp.md)   
 [コンテナー : クライアント アイテムへの通知](../mfc/containers-client-item-notifications.md)   
 [トラッカー](../mfc/trackers.md)   
 [CRectTracker クラス](../mfc/reference/crecttracker-class.md)