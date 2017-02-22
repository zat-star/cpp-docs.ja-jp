---
title: "スレッド モデルとクリティカル セクション クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.threads.models"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, クリティカル セクション"
  - "ATL, マルチスレッド"
  - "クリティカル セクション"
  - "スレッド処理 [ATL], モデル"
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# スレッド モデルとクリティカル セクション クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のクラスはスレッド モデルとクリティカル セクションを定義します:  
  
-   [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) は、スレッドのプールされているアパートメント モデル COM サーバーを実装します。  
  
-   [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) は、スレッドのプールされているアパートメント モデル COM サーバーを実装するためのメソッドを提供します。  
  
-   [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) は、変数をインクリメントおよびデクリメントするためのスレッドセーフなメソッドが用意されています。  クリティカル セクションを提供します。  
  
-   [CComMultiThreadModelNoCS](../Topic/CComMultiThreadModelNoCS%20Class.md) は、変数をインクリメントおよびデクリメントするためのスレッドセーフなメソッドが用意されています。  クリティカル セクションは用意されていません。  
  
-   [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) は、変数をインクリメントおよびデクリメントするためのメソッドを提供します。  クリティカル セクションは用意されていません。  
  
-   [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) は単一のオブジェクト クラスの適切なスレッド モデルのクラスを決定します。  
  
-   [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md) はグローバルに使用できるオブジェクトの適切なスレッド処理モデルのクラスを決定します。  
  
-   [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) はクリティカル セクションを取得および解放するメソッドが含まれています。  クリティカル セクションは自動的に初期化されます。  
  
-   [CComCriticalSection](../Topic/CComCriticalSection%20Class.md) はクリティカル セクションを取得および解放するメソッドが含まれています。  クリティカル セクションは明示的に初期化する必要があります。  
  
-   [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) は、クリティカル セクションを指定しないで `CComCriticalSection` のメソッドを反映します。  `CComFakeCriticalSection` のメソッドは何も実行しません。  
  
-   [CRTThreadTraits](../Topic/CRTThreadTraits%20Class.md) は、CRT スレッド用の作成関数が用意されています。  スレッドが CRT 関数を使用する場合に、このクラスを使用します。  
  
-   [Win32ThreadTraits](../Topic/Win32ThreadTraits%20Class.md) は、Windows スレッド用の作成関数が用意されています。  スレッドが CRT 関数を使用しない場合は、このクラスを使用します。  
  
## 参照  
 [クラスの概要](../atl/atl-class-overview.md)