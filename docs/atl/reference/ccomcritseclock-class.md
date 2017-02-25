---
title: "CComCritSecLock クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComCritSecLock"
  - "ATL.CComCritSecLock<TLock>"
  - "ATL::CComCritSecLock<TLock>"
  - "ATL.CComCritSecLock"
  - "CComCritSecLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCritSecLock クラス"
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComCritSecLock クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、クリティカル セクション オブジェクトをロックおよびロック解除するためのメソッドが用意されています。  
  
## 構文  
  
```  
  
      template<  
   class TLock  
> class CComCritSecLock  
```  
  
#### パラメーター  
 *TLock*  
 ロックおよびロックを解除するオブジェクト。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComCritSecLock::CComCritSecLock](../Topic/CComCritSecLock::CComCritSecLock.md)|コンストラクターです。|  
|[CComCritSecLock::~CComCritSecLock](../Topic/CComCritSecLock::~CComCritSecLock.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComCritSecLock::Lock](../Topic/CComCritSecLock::Lock.md)|クリティカル セクション オブジェクトをロックするには、このメソッドを呼び出します。|  
|[CComCritSecLock::Unlock](../Topic/CComCritSecLock::Unlock.md)|クリティカル セクション オブジェクトのロックを解除するには、このメソッドを呼び出します。|  
  
## 解説  
 [CComCriticalSection のクラス](../Topic/CComCriticalSection%20Class.md) または [CComAutoCriticalSection のクラス](../../atl/reference/ccomautocriticalsection-class.md)のより安全な方法でオブジェクトをロックしたり、ロックを解除するには、このクラスを使用します。  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 参照  
 [CComCriticalSection クラス](../Topic/CComCriticalSection%20Class.md)   
 [CComAutoCriticalSection クラス](../../atl/reference/ccomautocriticalsection-class.md)