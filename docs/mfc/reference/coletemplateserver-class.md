---
title: "COleTemplateServer クラス | Microsoft Docs"
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
  - "COleTemplateServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "オートメーション サーバー [C++], 実装"
  - "COleTemplateServer クラス"
  - "リンク コンテナー [C++]"
  - "OLE リンク コンテナー"
  - "OLE サーバー アプリケーション, COleTemplateServer クラス"
  - "OLE サーバー アプリケーション, 管理 (サーバー ドキュメントの)"
  - "サーバー, OLE"
  - "ビジュアル編集, サーバー"
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleTemplateServer クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE のビジュアル編集サーバー、オートメーション サーバー、およびリンク コンテナー \(埋め込みアイテムへのリンクをサポートするアプリケーションのことです\) で使います。  
  
## 構文  
  
```  
class COleTemplateServer : public COleObjectFactory  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleTemplateServer::COleTemplateServer](../Topic/COleTemplateServer::COleTemplateServer.md)|`COleTemplateServer` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleTemplateServer::ConnectTemplate](../Topic/COleTemplateServer::ConnectTemplate.md)|`COleObjectFactory` の基になるオブジェクトには、ドキュメント テンプレートを接続します。|  
|[COleTemplateServer::Unregister](../Topic/COleTemplateServer::Unregister.md)|関連するドキュメント テンプレートを登録解除します。|  
|[COleTemplateServer::UpdateRegistry](../Topic/COleTemplateServer::UpdateRegistry.md)|OLE システム レジストリを使用してドキュメントの種類を登録します。|  
  
## 解説  
 このクラスはクラスから派生します [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); 通常、それぞれ独自のクラスを派生ではなく `COleTemplateServer` を直接使用します。  `COleTemplateServer` はサーバー上のドキュメントの管理に [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) のオブジェクトを使用します。  フル サーバー、スタンドアロン アプリケーションとして実行できるつまり、サーバーを実装する場合は `COleTemplateServer` を使用します。  フル サーバーはシングル ドキュメント インターフェイス \(SDI \(SDI\) アプリケーションがサポートされているが、通常は、ドキュメント Interface \(MDI\) の複数のアプリケーションです。  `COleTemplateServer` の 1 種類のオブジェクトはサーバー上のドキュメントの種類ごとに必要です;アプリケーションのサポート つまり、サーバー アプリケーションがワークシートとグラフの両方をサポートする場合は、`COleTemplateServer` の 2 種類のオブジェクトが必要です。  
  
 `COleTemplateServer` は `COleObjectFactory`で定義されている `OnCreateInstance` のメンバー関数をオーバーライドします。  このメンバー関数は、フレームワークによって適切な型の C.C\+\+ オブジェクトを作成するために呼び出されます。  
  
 Server の詳細については、" " [サーバー: サーバーの実装](../../mfc/servers-implementing-a-server.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)  
  
 `COleTemplateServer`  
  
## 必要条件  
 **ヘッダー :** afxdisp.h  
  
## 参照  
 [MFC HIERSVR サンプル](../../top/visual-cpp-samples.md)   
 [COleObjectFactory クラス](../../mfc/reference/coleobjectfactory-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleServerDoc クラス](../Topic/COleServerDoc%20Class.md)   
 [COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)