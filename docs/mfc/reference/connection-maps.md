---
title: "コネクション マップ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コネクション マップ"
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コネクション マップ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE コントロールは、他のアプリケーションにインターフェイスをさらせます。  これらのインターフェイスは、コントロールにのみコンテナーからのアクセスを可能にします。  OLE コントロールが他の OLE オブジェクトの外部インターフェイスにアクセスする場合は、コネクション ポイントを確立する必要があります。  このコネクション ポイントは、コントロールにイベント マップまたは通知関数などの外部ディスパッチ マップ出力へのアクセスを提供します。  
  
 Microsoft Foundation Class ライブラリには、コネクション ポイントをサポートするプログラミング モデルが用意されています。  このモデルでは、OLE コントロールのインターフェイスまたはコネクション ポイントを指定するには、「コネクション マップ」が使用されます。  コネクション マップは、コネクション ポイントの 1 種類のマクロが含まれています。  コネクション マップの詳細については、[CConnectionPoint](../Topic/CConnectionPoint%20Class.md) クラスを参照します。  
  
 通常、コントロールは、2 種類のコネクション ポイントをサポートする: イベントの 1 とプロパティの通知の場合は 1。  これらは `COleControl` の基本クラスによって実装され、コントロールの作成者によって追加の作業は必要ではありません。  このクラスで実装したい他のコネクション ポイントは、手動で追加する必要があります。  コネクション マップとポイントをサポートするために、MFC では次のマクロが用意されています。:  
  
### コネクション マップの宣言と区切り  
  
|||  
|-|-|  
|[BEGIN\_CONNECTION\_PART](../Topic/BEGIN_CONNECTION_PART.md)|追加コネクション ポイントを実装する埋め込まれたなクラスを宣言します。クラスの宣言の中で使用する必要があります。|  
|[END\_CONNECTION\_PART](../Topic/END_CONNECTION_PART.md)|コネクション ポイントの宣言を終了します。クラスの宣言の中で使用する必要があります。|  
|[CONNECTION\_IID](../Topic/CONNECTION_IID.md)|コントロールのコネクション ポイント インターフェイスの ID を指定します。|  
|[DECLARE\_CONNECTION\_MAP](../Topic/DECLARE_CONNECTION_MAP.md)|コネクション マップはクラスで使用することを宣言します。クラスの宣言の中で使用する必要があります。|  
|[BEGIN\_CONNECTION\_MAP](../Topic/BEGIN_CONNECTION_MAP.md)|コネクション マップの定義を開始します。クラスの実装の中で使用する必要があります。|  
|[END\_CONNECTION\_MAP](../Topic/END_CONNECTION_MAP.md)|コネクション マップの定義を終了します。クラスの実装の中で使用する必要があります。|  
|[CONNECTION\_PART](../Topic/CONNECTION_PART.md)|コントロールのコネクション マップのコネクション ポイントを指定します。|  
  
 次の関数は、コネクション ポイントを使用して接続を確立し、クリッピング シンクの T:  
  
### コネクション ポイントの初期化と終了  
  
|||  
|-|-|  
|[AfxConnectionAdvise](../Topic/AfxConnectionAdvise.md)|ソース シンクとの間の接続を確立します。|  
|[AfxConnectionUnadvise](../Topic/AfxConnectionUnadvise.md)|ソース シンクとの間の接続を解除します。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)