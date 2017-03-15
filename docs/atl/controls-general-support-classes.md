---
title: "コントロール : 標準サポート クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.controls"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コントロール [ATL]"
  - "標準サポート クラス"
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# コントロール : 標準サポート クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のクラスは、ATL コントロールに一般的なサポートが用意されています:  
  
-   [CComControl](../atl/reference/ccomcontrol-class.md) ヘルパー関数は ATL コントロールに必要なデータ メンバーで構成されます。  
  
-   [IOleControlImpl](../atl/reference/iolecontrolimpl-class.md) は、コントロールに必要なメソッドが用意されています。  
  
-   [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md)、コンテナーがコントロールと通信する主なメソッドを提供します。  埋め込み先のコントロールのアクティブ化および非アクティブ化を管理します。  
  
-   遅延を避けるためにコンテナーを支援する単一の呼び出しの[IQuickActivateImpl](../atl/reference/iquickactivateimpl-class.md) の 結合の初期化時の読み込みのコントロール。  
  
-   [IPointerInactiveImpl](../atl/reference/ipointerinactiveimpl-class.md) は安全でないアクティブなコントロールに最小限のマウス操作を提供します。  
  
## サンプル プログラム  
 [ATLFire](../top/visual-cpp-samples.md)  
  
## 関連トピック  
 [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)  
  
## 参照  
 [クラスの概要](../atl/atl-class-overview.md)