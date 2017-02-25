---
title: "CMultiLock クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMultiLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiLock クラス"
  - "同期オブジェクト, アクセス制御"
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMultiLock クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マルチスレッド プログラムで複数のリソースのアクセス制御に使うアクセス コントロール機構を表します。  
  
## 構文  
  
```  
class CMultiLock  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMultiLock::CMultiLock](../Topic/CMultiLock::CMultiLock.md)|`CMultiLock` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMultiLock::IsLocked](../Topic/CMultiLock::IsLocked.md)|配列の特定の同期オブジェクトがロックされているかどうかを判定します。|  
|[CMultiLock::Lock](../Topic/CMultiLock::Lock.md)|同期オブジェクトの配列を待機します。|  
|[CMultiLock::Unlock](../Topic/CMultiLock::Unlock.md)|所有された同期オブジェクトを解放します。|  
  
## 解説  
 `CMultiLock` には、基本クラスはありません。  
  
 同期クラスを [CSemaphore](../../mfc/reference/csemaphore-class.md)、[CMutex](../../mfc/reference/cmutex-class.md)使用するには、[CEvent](../../mfc/reference/cevent-class.md)の待機する **CMultiLock** か [CSingleLock](../../mfc/reference/csinglelock-class.md) のオブジェクトを作成し、同期オブジェクトを解放できます。  ユーザーが特定の時刻に使用できる複数のオブジェクトがある場合 **CMultiLock** を使用します。  だけ 1 種類のオブジェクトに一度に待機する必要がある場合 `CSingleLock` を使用します。  
  
 待機することに **CMultiLock** のオブジェクトを使用するには、最初に同期の配列をオブジェクトを作成します。  次に、マネージ リソース クラスのメンバー関数の中の **CMultiLock** オブジェクトのコンストラクターを呼び出します。  次に、リソースが使用可能かどうかを確認するに [&#91;ロック&#93;](../Topic/CMultiLock::Lock.md) のメンバー関数を呼び出します \(シグナル状態\)。  が 1 の場合は、メンバー関数の残りの部分を続行します。  リソースが使用可能でない場合は、解放されるリソースの一定の時間待機するかまたは失敗を返します。  リソースの使用が完了したら、**CMultiLock** のオブジェクトが再び使用する場合は、いずれかの呼び出しは [&#91;ロック解除&#93;](../Topic/CMultiLock::Unlock.md) 関数または **CMultiLock** のオブジェクトが破棄されるようにします。  
  
 **CMultiLock** のオブジェクトは、スレッドに応答できる `CEvent` のオブジェクトが複数ある場合に便利です。  `CEvent` のすべてのポインターを含む配列を作成し `Lock`を呼び出します。  イベントの 1 つがシグナル状態になるまでこれにより、スレッドを待機させます。  
  
 **CMultiLock** のオブジェクトを使用する方法の詳細については、" " [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)を参照してください。  
  
## 継承階層  
 `CMultiLock`  
  
## 必要条件  
 **ヘッダー :** afxmt.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)