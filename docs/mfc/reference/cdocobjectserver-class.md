---
title: "CDocObjectServer クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDocObjectServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX ドキュメント [C++], ドキュメント サーバー"
  - "CDocObjectServer クラス"
  - "docobject サーバー"
  - "ドキュメント オブジェクト サーバー"
  - "サーバー [C++], ActiveX ドキュメント"
  - "サーバー [C++], doc オブジェクト"
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDocObjectServer クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

標準の `COleDocument` サーバーを完全な DocObject サーバーにするために必要な、`IOleDocument`、`IOleDocumentView`、`IOleCommandTarget`、`IPrint` などの追加 OLE インターフェイスを実装します。  
  
## 構文  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDocObjectServer::CDocObjectServer](../Topic/CDocObjectServer::CDocObjectServer.md)|`CDocObjectServer` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDocObjectServer::ActivateDocObject](../Topic/CDocObjectServer::ActivateDocObject.md)|ドキュメント オブジェクトのサーバーをアクティブにしますが、は含まれません。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDocObjectServer::OnActivateView](../Topic/CDocObjectServer::OnActivateView.md)|DocObject のビューが表示されます。|  
|[CDocObjectServer::OnApplyViewState](../Topic/CDocObjectServer::OnApplyViewState.md)|DocObject のビューの状態を復元します。|  
|[CDocObjectServer::OnSaveViewState](../Topic/CDocObjectServer::OnSaveViewState.md)|DocObject のビューの状態を保存します。|  
  
## 解説  
 `CDocObjectServer` は `COleServerDoc` と `CCmdTarget` と作業からインターフェイスを公開するために密接に取得されます。  
  
 DocObject サーバーのドキュメントは、DocObject の項目をサーバー インターフェイスを表す [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) のオブジェクトを含めることができます。  
  
 の DocObject サーバーをカスタマイズするには、独自のクラスを `CDocObjectServer` から派生し、ビューをオーバーライドする関数、[OnActivateView](../Topic/CDocObjectServer::OnActivateView.md)、[OnApplyViewState](../Topic/CDocObjectServer::OnApplyViewState.md)と [OnSaveViewState](../Topic/CDocObjectServer::OnSaveViewState.md)を設定します。  フレームワークの呼び出しに応答して、クラスの新しいインスタンスを提供する必要があります。  
  
 DocObjects の詳細については、*" MFC リファレンス"*の [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) と [COleCmdUI](../../mfc/reference/colecmdui-class.md) を参照してください。  また [インターネットの対処方法: Active ドキュメント](../Topic/Active%20Documents%20on%20the%20Internet.md) と [Active ドキュメント](../Topic/Active%20Documents%20on%20the%20Internet.md)を参照してください。  
  
 また、次のサポート技術情報の文書を参照:  
  
-   Q247382: PRB: ActiveX ドキュメント サーバー コントロールのツールヒントは、ActiveX ドキュメント コンテナーによって非表示になります  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `CDocObjectServer`  
  
## 必要条件  
 **Header:** afxdocob.h  
  
## 参照  
 [CCmdTarget クラス](../Topic/CCmdTarget%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDocObjectServerItem クラス](../../mfc/reference/cdocobjectserveritem-class.md)