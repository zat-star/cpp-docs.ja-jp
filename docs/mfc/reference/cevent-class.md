---
title: "CEvent クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CEvent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEvent クラス"
  - "同期クラス, CEvent クラス"
  - "同期オブジェクト, event"
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CEvent クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

イベントを表します。これは、あるスレッドから別のスレッドにイベントの発生を通知できるようにする同期オブジェクトです。  
  
## 構文  
  
```  
class CEvent : public CSyncObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CEvent::CEvent](../Topic/CEvent::CEvent.md)|`CEvent` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CEvent::PulseEvent](../Topic/CEvent::PulseEvent.md)|使用できる \(シグナル状態\)、リリースの待機中のスレッドおよび使用不可能にセットにイベントをイベント設定します \(非シグナル状態\)。|  
|[CEvent::ResetEvent](../Topic/CEvent::ResetEvent.md)|使用不可能に設定します \(nonsignaled\)。|  
|[CEvent::SetEvent](../Topic/CEvent::SetEvent.md)|使用できる \(シグナル状態\) とリリースにすべてのイベントを待機スレッド設定します。|  
|[CEvent::Unlock](../Topic/CEvent::Unlock.md)|イベント オブジェクトを解放します。|  
  
## 解説  
 イベントは、スレッドがタスクを実行するタイミングを知る必要がある場合に役立ちます。  たとえば、データをデータ アーカイブにコピーするスレッドは、新しいデータが利用できるようになったときに通知される必要があります。  新しいデータが利用できるようになったとき、`CEvent` オブジェクトを使ってコピーを行うスレッドに通知をすると、スレッドはすぐにコピーを行うことができます。  
  
 `CEvent` オブジェクトには、手動と自動の 2 つの型があります。  
  
 自動の `CEvent` オブジェクトは、少なくとも 1 つのスレッドが解放されると、自動的に非シグナル状態 \(利用できない状態\) になります。  既定では、構築時に `bManualReset` パラメーターに `TRUE` を渡さない限り、`CEvent` オブジェクトは自動になります。  
  
 手動の `CEvent` オブジェクトは、他の関数が呼び出されるまで [SetEvent](../Topic/CEvent::SetEvent.md) または [ResetEvent](../Topic/CEvent::ResetEvent.md) で設定された状態を維持します。  手動の `CEvent` オブジェクトを作成するには、構築時に `bManualReset` パラメーターに `TRUE` を渡します。  
  
 `CEvent` オブジェクトを使用するには、必要になったときに `CEvent` オブジェクトを構築します。  待機するイベント名を指定すると共に、そのイベントを最初はアプリケーションが所有するように指定します。  コンストラクターから戻るとイベントにアクセスできます。  [SetEvent](../Topic/CEvent::SetEvent.md) を呼び出してイベント オブジェクトをシグナル状態 \(利用できる状態\) にします。その後、制御されるリソースへのアクセス終了時に [Unlock](../Topic/CEvent::Unlock.md) を呼び出します。  
  
 `CEvent` オブジェクトのもう 1 つの使い方は、制御するクラスのデータ メンバーとして、`CEvent` 型の変数を追加することです。  制御されるオブジェクトの構築中に、`CEvent` データ メンバーのコンストラクターを呼び出し、イベントを最初にシグナル状態にするかどうか、使用するイベント オブジェクトの型、イベント名 \(プロセス境界をまたいで使用する場合\)、および必要なセキュリティ属性を指定します。  
  
 この方法で `CEvent` オブジェクトが制御しているリソースにアクセスするには、まず、リソースにアクセスするメソッド内に [CSingleLock](../../mfc/reference/csinglelock-class.md) 型または [CMultiLock](../../mfc/reference/cmultilock-class.md) 型の変数を作成します。  次に、ロック オブジェクトの `Lock` メソッド \(たとえば [CMultiLock::Lock](../Topic/CMultiLock::Lock.md)\) を呼び出します。  この時点で、スレッドは、リソースへのアクセスを獲得するか、リソースが解放されてアクセスできるようになるまで待つか、リソースの解放を待っている間にタイムアウトが発生し、リソースへのアクセスに失敗するかのいずれかの状態になります。  いずれの場合も、リソースはスレッド セーフな方法でアクセスされています。  リソースを解放するには `SetEvent` を呼び出してイベント オブジェクトをシグナル状態にした後、ロック オブジェクトの `Unlock` メソッド \(たとえば [CMultiLock::Unlock](../Topic/CMultiLock::Unlock.md)\) を使用するか、ロック オブジェクトがスコープ外になるようにします。  
  
 `CEvent` オブジェクトを使用する方法の詳細については、「[マルチスレッド: 同期クラスの使用法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。  
  
## 使用例  
 [!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/CPP/cevent-class_1.cpp)]  
  
 [!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/CPP/cevent-class_2.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CEvent`  
  
## 必要条件  
 **ヘッダー :** afxmt.h  
  
## 参照  
 [CSyncObject クラス](../../mfc/reference/csyncobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)