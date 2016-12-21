---
title: "CMutex クラス | Microsoft Docs"
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
  - "Mutex"
  - "CMutex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMutex クラス"
  - "ミューテックス"
  - "同期クラス, CMutex クラス"
  - "同期オブジェクト, ミューテックス"
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMutex クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

「ミューテックスを」— 1 "のスレッドがリソースに排他アクセスできるようにする同期オブジェクトを表します。  
  
## 構文  
  
```  
class CMutex : public CSyncObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMutex::CMutex](../Topic/CMutex::CMutex.md)|`CMutex` オブジェクトを構築します。|  
  
## 解説  
 ミューテックスには 1 種類のスレッドは一度にデータまたは他のマネージ リソースを変更できるようになるある場合に便利です。  たとえば、リンク リストにノードを追加するには、1 種類のスレッドによって一度に与える必要なプロセスです。  リンク リストを制御するために `CMutex` のオブジェクトを使用して 1 一つのスレッドだけがリストに同時にアクセス権を得ることができます。  
  
 必要な場合 `CMutex` のオブジェクトを使用するには、`CMutex` のオブジェクトを構築します。  アプリケーションが最初に、要素を所有することで待機するミューテックスの名前を指定します。  コンストラクターから戻るとミューテックスにアクセスできます。  被制御リソースにアクセスすると [CSyncObject::Unlock](../Topic/CSyncObject::Unlock.md) を呼び出します。  
  
 `CMutex` のオブジェクトを使用するための代替メソッドは、制御するクラスのデータ メンバーとして、`CMutex` 型の変数を追加することです。  マネージ オブジェクトの構築時に、`CMutex` データ メンバーのミューテックスを所有されると最初に指定すると、ミューテックス \(プロセス境界をまたいで使用する場合\) 名前、および必要なセキュリティ属性のコンストラクターを呼び出します。  
  
 最初に制御されているリソースにアクセスする [CSingleLock](../../mfc/reference/csinglelock-class.md) 型の変数を作成したり、リソースにアクセスのメンバー関数の [CMultiLock](../../mfc/reference/cmultilock-class.md) を入力するに `CMutex` のこの方法でオブジェクト。  次に、ロック オブジェクトの `Lock` のメンバー関数 \( [CSingleLock::Lock](../Topic/CSingleLock::Lock.md)\) を呼び出します。  この時点で、スレッドは、リソースが解放されるリソースの待機時間にアクセス権を獲得、アクセス権を獲得するか、待機し、リソースを解放すると時間など、リソースへのアクセスを表示できないことができます。  いずれの場合も、リソースはスレッド セーフな方法でアクセスされています。  リソースを解放する、ロック オブジェクトの `Unlock` のメンバー関数 \(たとえば、\) [CSingleLock::Unlock](../Topic/CSingleLock::Unlock.md)使用する、またはスコープから離れるへのロック オブジェクトを許可します。  
  
 `CMutex` のオブジェクトの使用の詳細については、" " [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CMutex`  
  
## 必要条件  
 **ヘッダー :** afxmt.h  
  
## 参照  
 [CSyncObject クラス](../../mfc/reference/csyncobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)