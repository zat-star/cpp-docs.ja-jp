---
title: "ワーカー用原型クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ワーカー用原型クラス"
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
caps.latest.revision: 16
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ワーカー用原型クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

*ワーカー* 元に準拠するクラスはスレッド プールにキューイング プロセス作業項目にコードを提供します。  
  
 **実装**  
  
 この元に従ってクラスを実装するには、クラスには次の機能を提供する必要があります:  
  
|メソッド|説明|  
|----------|--------|  
|[初期化](../Topic/WorkerArchetype::Initialize.md)|要求の前にワーカー オブジェクトを初期化するために呼び出されます [&#91;実行&#93;](../Topic/WorkerArchetype::Execute.md)に渡されます。|  
|[実行](../Topic/WorkerArchetype::Execute.md)|作業項目を処理するために呼び出されます。|  
|[終了](../Topic/WorkerArchetype::Terminate.md)|すべての要求が [&#91;実行&#93;](../Topic/WorkerArchetype::Execute.md)に渡された後でワーカー オブジェクトの初期化を解除するために呼び出されます。|  
  
|typedef|説明|  
|-------------|--------|  
|[RequestType](../Topic/WorkerArchetype::RequestType.md)|ワーカー クラスで処理できる作業項目の種類の typedef。|  
  
 一般的な *ワーカー* クラスは次のようになります。:  
  
 [!CODE [NVC_ATL_Utilities#137](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#137)]  
  
 **既存の実装**  
  
 これらのクラスはこの元に準拠しています:  
  
|Class|説明|  
|-----------|--------|  
|[CNonStatelessWorker](../Topic/CNonStatelessWorker%20Class.md)|スレッド プールからの要求を受け取り、要求ごとに作成したり破棄されるワーカー オブジェクトに渡します。|  
  
 **使用**  
  
 これらのテンプレート パラメーターはこの元に準拠するとクラスを想定しています:  
  
|\[パラメーター名\]|使用するコントロール|  
|-----------------|----------------|  
|*\[ワーカ\]*|[CThreadPool](../Topic/CThreadPool%20Class.md)|  
|*\[ワーカ\]*|[CNonStatelessWorker](../Topic/CNonStatelessWorker%20Class.md)|  
  
## 要件  
 **Header:** atlutil.h  
  
## 参照  
 [原型](../../atl/reference/atl-archetypes.md)   
 [概念](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)