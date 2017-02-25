---
title: "COleMessageFilter クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleMessageFilter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アプリケーション [OLE], 管理 (対話を)"
  - "COleMessageFilter クラス"
  - "メッセージ フィルター [C++]"
  - "メッセージ [C++], OLE"
  - "OLE [C++], 管理 (同時実行を)"
  - "OLE アプリケーション [C++], 管理 (対話を)"
  - "OLE メッセージ"
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# COleMessageFilter クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE アプリケーション間の相互の要求を同時に管理します。  
  
## 構文  
  
```  
class COleMessageFilter : public CCmdTarget  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleMessageFilter::COleMessageFilter](../Topic/COleMessageFilter::COleMessageFilter.md)|`COleMessageFilter` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleMessageFilter::BeginBusyState](../Topic/COleMessageFilter::BeginBusyState.md)|ビジー状態にアプリケーションを設定します。|  
|[COleMessageFilter::EnableBusyDialog](../Topic/COleMessageFilter::EnableBusyDialog.md)|呼び出されたアプリケーションがビジー状態であるときに表示されるダイアログ ボックスを有効または無効にします。|  
|[COleMessageFilter::EnableNotRespondingDialog](../Topic/COleMessageFilter::EnableNotRespondingDialog.md)|呼び出されたアプリケーションが応答しないときに表示されるダイアログ ボックスを有効または無効にします。|  
|[COleMessageFilter::EndBusyState](../Topic/COleMessageFilter::EndBusyState.md)|アプリケーションのビジー状態を終了します。|  
|[COleMessageFilter::OnMessagePending](../Topic/COleMessageFilter::OnMessagePending.md)|OLE 呼び出しの実行中に、メッセージを処理するために、フレームワークによって呼び出されます。|  
|[COleMessageFilter::Register](../Topic/COleMessageFilter::Register.md)|OLE システム DLL のメッセージ フィルターを登録します。|  
|[COleMessageFilter::Revoke](../Topic/COleMessageFilter::Revoke.md)|OLE システム DLL のメッセージ フィルターの登録を取り消します。|  
|[COleMessageFilter::SetBusyReply](../Topic/COleMessageFilter::SetBusyReply.md)|OLE 呼び出しにビジー状態でアプリケーションの応答を決定します。|  
|[COleMessageFilter::SetMessagePendingDelay](../Topic/COleMessageFilter::SetMessagePendingDelay.md)|アプリケーションが OLE 呼び出しに対する応答を待機するかを判定します。|  
|[COleMessageFilter::SetRetryReply](../Topic/COleMessageFilter::SetRetryReply.md)|ビジー状態でアプリケーションへの呼び出し元のアプリケーションの応答を決定します。|  
  
## 解説  
 `COleMessageFilter` のクラスは、ビジュアル編集サーバーとコンテナー アプリケーション、または OLE オートメーション アプリケーションに便利です。  呼び出し元のアプリケーション「中」にするためにサーバー アプリケーションのほかのコンテナー アプリケーションからの受信後で、キャンセルまたは再試行したように、このクラスを使用できます。  呼び出されたアプリケーションがビジー状態である場合にもこのクラスが呼び出し元のアプリケーションで実行されるアクションを決定するために使用できます。  
  
 一般的には [BeginBusyState](../Topic/COleMessageFilter::BeginBusyState.md) と [EndBusyState](../Topic/COleMessageFilter::EndBusyState.md) を呼び出すサーバー アプリケーションでは、が破棄されるドキュメントまたは別の OLE アクセスできるオブジェクトに危険な場合があります。  この呼び出しは、ユーザー インターフェイス更新中に [CWinApp::OnIdle](../Topic/CWinApp::OnIdle.md) で作成されます。  
  
 既定では、`COleMessageFilter` のオブジェクトは、アプリケーションが初期化されるときに割り当てられます。  これは [AfxOleGetMessageFilter](../Topic/AfxOleGetMessageFilter.md)で取得できます。  
  
 これは、高度なクラスです。; ほとんどそれを直接使用する必要はありません。  
  
 詳細については、" " [サーバー: サーバーの実装](../../mfc/servers-implementing-a-server.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `COleMessageFilter`  
  
## 必要条件  
 **Header:** afxole.h  
  
## 参照  
 [CCmdTarget クラス](../Topic/CCmdTarget%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdTarget クラス](../Topic/CCmdTarget%20Class.md)