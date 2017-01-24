---
title: "CSingleLock クラス | Microsoft Docs"
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
  - "CSingleLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSingleLock クラス"
  - "同期オブジェクト, アクセス制御"
  - "スレッド処理 [MFC], アクセス制御"
  - "スレッド処理 [MFC], 同期"
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSingleLock クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マルチスレッド プログラムで 1 つのリソースのアクセス制御に使うアクセス コントロール機構を表します。  
  
## 構文  
  
```  
  
class CSingleLock  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSingleLock::CSingleLock](../Topic/CSingleLock::CSingleLock.md)|`CSingleLock` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSingleLock::IsLocked](../Topic/CSingleLock::IsLocked.md)|オブジェクトがロックされているかどうかを判定します。|  
|[CSingleLock::Lock](../Topic/CSingleLock::Lock.md)|同期オブジェクトのを待ちます。|  
|[CSingleLock::Unlock](../Topic/CSingleLock::Unlock.md)|同期オブジェクトを解放します。|  
  
## 解説  
 `CSingleLock` には、基本クラスはありません。  
  
 同期クラスを [CSemaphore](../../mfc/reference/csemaphore-class.md)、[CMutex](../../mfc/reference/cmutex-class.md)使用するには、[CCriticalSection](../Topic/CCriticalSection%20Class.md)と [CEvent](../../mfc/reference/cevent-class.md)の待機する `CSingleLock` か [CMultiLock](../../mfc/reference/cmultilock-class.md) のオブジェクトを作成し、同期オブジェクトを解放する必要があります。  だけ 1 種類のオブジェクトに一度に待機する必要がある場合 `CSingleLock` を使用します。  ユーザーが特定の時刻に使用できる複数のオブジェクトがある場合 **CMultiLock** を使用します。  
  
 `CSingleLock` のオブジェクトを使用するには、マネージ リソース クラスのメンバー関数の中のコンストラクターを呼び出します。  次に、リソースが使用可能かどうかを確認するに [IsLocked](../Topic/CSingleLock::IsLocked.md) のメンバー関数を呼び出します。  そうである場合、メンバー関数の残りの部分を続行します。  リソースが使用できない場合は、解放されるリソースの一定の時間待機するかまたは失敗を返します。  リソースの使用が完了したら、`CSingleLock` のオブジェクトが再び使用する場合は、いずれかの呼び出しは [&#91;ロック解除&#93;](../Topic/CSingleLock::Unlock.md) 関数または `CSingleLock` のオブジェクトが破棄されるようにします。  
  
 `CSingleLock` のオブジェクトは [CSyncObject](../../mfc/reference/csyncobject-class.md)から派生したオブジェクトが存在する必要があります。  これは通常、マネージ リソース クラスのデータ メンバーです。  `CSingleLock` のオブジェクトを使用する方法の詳細については、" " [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)を参照してください。  
  
## 継承階層  
 `CSingleLock`  
  
## 必要条件  
 **ヘッダー :** afxmt.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMultiLock クラス](../../mfc/reference/cmultilock-class.md)