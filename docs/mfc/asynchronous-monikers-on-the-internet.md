---
title: "インターネット上の非同期モニカー | Microsoft Docs"
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
  - "ActiveX コントロール [C++], 非同期"
  - "非同期モニカー [C++]"
  - "ダウンロード (インターネット リソースのダウンロードと非同期モニカー)"
  - "インターネット [C++], 非同期のダウンロード"
  - "MFC [C++], 非同期モニカー"
  - "最適化 [C++], 非同期のダウンロード (インターネット)"
  - "Web アプリケーション [C++], 非同期"
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# インターネット上の非同期モニカー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

インターネットは、低速のネットワーク アクセスのアプリケーションの設計に新しい方法が必要です。  アプリケーションのユーザー インターフェイスを停止しないようにネットワーク アクセスを非同期的に実行する必要があります。  MFC クラス [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) はファイルをダウンロードする非同期サポートを提供します。  
  
 非同期モニカーを使用すると、インターネット経由で非同期にダウンロードし、ビットマップ、VRML オブジェクトなどの大きいオブジェクトの推移的な描画を提供する COM アプリケーションを拡張できます。  非同期モニカーはユーザー インターフェイスの応答をブロックせずにダウンロードするインターネット上の ActiveX コントロール プロパティまたはファイルを有効にします。  
  
## 非同期モニカーの利点  
 非同期モニカーを使用する:  
  
-   ブロックせずにダウンロードとコード ファイル。  
  
-   ブロックせずに ActiveX コントロールのダウンロードのプロパティ。  
  
-   ダウンロードの進行状況の通知を受信します。  
  
-   進行状況と準備状態情報を追跡する。  
  
-   進行状況についてユーザーにステータス情報を表示します。  
  
-   ユーザーがダウンロードをいつでも取り消すことができます。  
  
## 非同期モニカーの MFC クラス  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) は [CMonikerFile](../Topic/CMonikerFile%20Class.md)から派生されます [COleStreamFile](../Topic/COleStreamFile%20Class.md)、から派生される。  `COleStreamFile` オブジェクトはデータのストリームを表します; `CMonikerFile` オブジェクトでは、データの取得に `IMoniker` を使用して `CAsyncMonikerFile` オブジェクトは、非同期的に使用します。  
  
 インターネット対応アプリケーションおよび ActiveX コントロールで非同期モニカーは、主にファイル転送中に重要なユーザー インターフェイスを提供するために使用されます。  これが最も良い例は ActiveX コントロールに非同期プロパティを提供する [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md) の使用です。  
  
## ActiveX コントロールのデータ パスの MFC クラス  
 MFC クラス `CDataPathProperty` と [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md) は非同期的に読み込むことができる ActiveX コントロール プロパティを実装します。  非同期プロパティは同期の開始後に読み込まれます。  非同期 ActiveX コントロールが繰り返し長い所持品の交換処理中に新しいデータが利用できるかどうかを示すために、コールバックを呼び出します。  
  
 `CDataPathProperty` は `CAsyncMonikerFile` から派生します。  `CCachedDataPathProperty` は `CDataPathProperty` から派生します。  ActiveX コントロールの非同期プロパティを実装するには、クラスを `CDataPathProperty` または `CCachedDataPathProperty`から派生し、受信する他の通知と [Ondataavailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md) をオーバーライドします。  
  
#### ファイルを非同期モニカーを使用してダウンロードします。  
  
1.  [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)から派生したクラスを宣言します。  
  
2.  データを表示するためにオーバーライド [Ondataavailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md)。  
  
3.  [OnProgress](../Topic/CAsyncMonikerFile::OnProgress.md)、[OnStartBinding](../Topic/CAsyncMonikerFile::OnStartBinding.md)と [OnStopBinding](../Topic/CAsyncMonikerFile::OnStopBinding.md)などの他のメンバー関数をオーバーライドします。  
  
4.  このクラスのインスタンスを宣言し、URL を開くために使用します。  
  
 ActiveX コントロールの非同期ダウンロードについては、[インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)を参照してください。  
  
## 参照  
 [MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)   
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)