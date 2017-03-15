---
title: "コンテナー : クライアント アイテムへの通知 | Microsoft Docs"
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
  - "通知, コンテナー クライアント アイテム"
  - "OLE コンテナー, クライアント アイテム通知"
ms.assetid: e1f1c427-01f5-45f2-b496-c5bce3d76340
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# コンテナー : クライアント アイテムへの通知
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、サーバー アプリケーションがクライアント アプリケーションのドキュメントの作業項目を変更するときに、フレームワークが呼び出しますオーバーライドできるな関数について説明します。  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md) は サーバー アプリケーションと呼ばれ、構成アプリケーションからの要求に対して、複数のオーバーライドできるな関数を定義します。  これらのオーバーライド可能な関数は、通常、通知として機能します。  これらは変更のスクロール、アクティブ化、または配置がなどのさまざまなイベントをコンテナー アプリケーションに、通知、そのユーザーにより、項目を編集すると、または別の方法で処理します。  
  
 フレームワークは、呼び出し、実装が必要なオーバーライドできるな関数によって `COleClientItem::OnChange`への変更のコンテナー アプリケーションに通知します。  この保護されたな関数は、2 個の引数を受け取ります。  1 番目のサーバーが項目を変更した理由を指定する:  
  
|通知|説明|  
|--------|--------|  
|`OLE_CHANGED`|OLE アイテムの外観が変更されました。|  
|`OLE_SAVED`|OLE アイテムが格納されています。|  
|`OLE_CLOSED`|OLE アイテムは閉じられました。|  
|**OLE\_RENAMED**|OLE アイテムを含むサーバー ドキュメントの名前が変更されました。|  
|`OLE_CHANGED_STATE`|OLE アイテムは 1 個の状態が変更されました。|  
|**OLE\_CHANGED\_ASPECT**|OLE アイテムのレンダリング機能はフレームワークによって変更されました。|  
  
 これらの値は AFXOLE.H.で定義されている **OLE\_NOTIFICATION** の列挙体からです。  
  
 この関数への 2 番目の引数は、項目がどのように変更されたか、どの状態を入力したかを指定する:  
  
|最初の引数がある場合|2 番目の引数|  
|----------------|-------------|  
|`OLE_SAVED` または `OLE_CLOSED`|使用されません。|  
|`OLE_CHANGED`|変更された OLE アイテムの要素を指定します。|  
|`OLE_CHANGED_STATE`|入力状態を説明しています \(`emptyState`、**loadedState**、`openState`、`activeState`、または `activeUIState`\)。|  
  
 クライアント項目を参照する [コンテナー: クライアント項目の状態](../mfc/containers-client-item-states.md)が使用できる状態に関する詳細について。  
  
 フレームワークは、項目が埋め込み先での編集に対してアクティブにする場合 `COleClientItem::OnGetItemPosition` を呼び出します。  実装は埋め込み先での編集をサポートするアプリケーションで必要です。  MFC アプリケーション ウィザードでは `OnGetItemPosition`に引数として渡す `CRect` オブジェクトに項目の座標を割り当てる基本実装を提供します。  
  
 OLE アイテムの位置とサイズを埋め込み先での編集中に変更されると、項目の位置に関する情報とコンテナーのクリッピング四角形は更新されなければ、サーバーは変更に関する情報を受け取る必要があります。  フレームワークは `COleClientItem::OnChangeItemPosition` をモデル化します。  MFC アプリケーション ウィザードでは、基本クラスの関数を呼び出すオーバーライドを提供します。  アプリケーション ウィザードで `COleClientItem`\-関数がクライアント項目オブジェクトが保持している情報を更新すると、派生クラスに対して記述関数を編集する必要があります。  
  
## 参照  
 [コンテナー](../mfc/containers.md)   
 [コンテナー : クライアント アイテムの状態](../mfc/containers-client-item-states.md)   
 [COleClientItem::OnChangeItemPosition](../Topic/COleClientItem::OnChangeItemPosition.md)