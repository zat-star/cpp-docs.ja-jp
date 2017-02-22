---
title: "CSyncObject クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSyncObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSyncObject クラス"
  - "同期クラス, CSyncObject"
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSyncObject クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Win32 の同期オブジェクトに共通の機能を提供する純粋仮想クラスです。  
  
## 構文  
  
```  
class CSyncObject : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSyncObject::CSyncObject](../Topic/CSyncObject::CSyncObject.md)|`CSyncObject` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSyncObject::Lock](../Topic/CSyncObject::Lock.md)|同期オブジェクトにアクセスできるようになります。|  
|[CSyncObject::Unlock](../Topic/CSyncObject::Unlock.md)|同期オブジェクトにアクセスできるようになります。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CSyncObject::operator HANDLE](../Topic/CSyncObject::operator%20HANDLE.md)|同期オブジェクトへのアクセスを提供します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CSyncObject::m\_hObject](../Topic/CSyncObject::m_hObject.md)|基になる同期オブジェクトへのハンドル。|  
  
## 解説  
 Microsoft Foundation Class ライブラリには `CSyncObject`から派生する複数のクラスを提供します。  これらは [CEvent](../../mfc/reference/cevent-class.md)、[CMutex](../../mfc/reference/cmutex-class.md)、[CCriticalSection](../Topic/CCriticalSection%20Class.md)と [CSemaphore](../../mfc/reference/csemaphore-class.md)です。  
  
 同期オブジェクトを使用する方法については、" " [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CSyncObject`  
  
## 必要条件  
 **ヘッダー :** afxmt.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)