---
title: "CSemaphore クラス | Microsoft Docs"
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
  - "CSemaphore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSemaphore クラス"
  - "セマフォ"
  - "同期オブジェクト, セマフォ"
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSemaphore クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

クラス `CSemaphore` のオブジェクトは「セマフォ」を表します—一つ以上のプロセスの限られた数のスレッドだけがリソースにアクセスできるようにする同期オブジェクトは、現在指定したリソースにアクセスするスレッドの数を保持します。  
  
## 構文  
  
```  
class CSemaphore : public CSyncObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSemaphore::CSemaphore](../Topic/CSemaphore::CSemaphore.md)|`CSemaphore` オブジェクトを構築します。|  
  
## 解説  
 セマフォは、ユーザーの限られた数をサポートできる共有リソースへのアクセスの制御に便利です。  `CSemaphore` のオブジェクトの現在の計算が許可される追加のユーザーの数です。  カウントがゼロに達すると、**CSemaphore** のオブジェクトによって制御されるリソースを使用するすべての試行はシステムのキューに挿入し、までの待機時間など、または計算は 0 以上に発生します。  マネージ リソースを同時にアクセスできるユーザーの最大数は `CSemaphore` のオブジェクトの構築時に指定されます。  
  
 必要な場合 **CSemaphore** のオブジェクトを使用するには、`CSemaphore` のオブジェクトを構築します。  アプリケーションが最初に、要素を所有することが待機する、セマフォの名前を指定します。  コンストラクターから戻るとセマフォにアクセスできます。  被制御リソースにアクセスすると [CSyncObject::Unlock](../Topic/CSyncObject::Unlock.md) を呼び出します。  
  
 `CSemaphore` のオブジェクトを使用するための代替メソッドは、制御するクラスのデータ メンバーとして、`CSemaphore` 型の変数を追加することです。  マネージ オブジェクトの構築時に、セマフォのカウントの初期のアクセス、最大のアクセスの計算および名前 \(プロセス境界をまたいで使用する場合\)、および必要なセキュリティ属性を指定する `CSemaphore` データ メンバーのコンストラクターを呼び出します。  
  
 最初に制御されているリソースにアクセスする [CSingleLock](../../mfc/reference/csinglelock-class.md) 型の変数を作成したり、リソースにアクセスのメンバー関数の [CMultiLock](../../mfc/reference/cmultilock-class.md) を入力するに `CSemaphore` のこの方法でオブジェクト。  次に、ロック オブジェクトの `Lock` のメンバー関数 \( [CSingleLock::Lock](../Topic/CSingleLock::Lock.md)\) を呼び出します。  この時点で、スレッドは、リソースが解放されるリソースの待機時間にアクセス権を獲得、アクセス権を獲得するか、待機し、リソースを解放すると時間など、リソースへのアクセスを表示できないことができます。  いずれの場合も、リソースはスレッド セーフな方法でアクセスされています。  リソースを解放する、ロック オブジェクトの `Unlock` のメンバー関数 \(たとえば、\) [CSingleLock::Unlock](../Topic/CSingleLock::Unlock.md)使用する、またはスコープから離れるへのロック オブジェクトを許可します。  
  
 また、**CSemaphore** のオブジェクトのスタンドアロンを作成し、被制御リソースにアクセスする前に明示的にアクセスします。  このメソッドは、がソース・コードを読む場合は、さらに明確によりエラーが発生しやすくなります。  
  
 **CSemaphore** のオブジェクトを使用する方法の詳細については、" " [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CSemaphore`  
  
## 必要条件  
 **ヘッダー :** afxmt.h  
  
## 参照  
 [CSyncObject クラス](../../mfc/reference/csyncobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)