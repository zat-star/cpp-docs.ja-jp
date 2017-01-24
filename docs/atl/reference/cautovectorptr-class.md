---
title: "CAutoVectorPtr クラス | Microsoft Docs"
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
  - "ATL::CAutoVectorPtr"
  - "ATL.CAutoVectorPtr"
  - "ATL.CAutoVectorPtr<T>"
  - "CAutoVectorPtr"
  - "ATL::CAutoVectorPtr<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoVectorPtr クラス"
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAutoVectorPtr クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、ベクターの new 演算子と delete 演算子を使用して、スマート ポインター オブジェクトを表します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
typename T  
> class CAutoVectorPtr  
```  
  
#### パラメーター  
 `T`  
 ポインター型。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAutoVectorPtr::CAutoVectorPtr](../Topic/CAutoVectorPtr::CAutoVectorPtr.md)|コンストラクターです。|  
|[CAutoVectorPtr::~CAutoVectorPtr](../Topic/CAutoVectorPtr::~CAutoVectorPtr.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAutoVectorPtr::Allocate](../Topic/CAutoVectorPtr::Allocate.md)|`CAutoVectorPtr`によってに指すオブジェクトの配列に必要なメモリを割り当てるには、このメソッドを呼び出します。|  
|[CAutoVectorPtr::Attach](../Topic/CAutoVectorPtr::Attach.md)|既存のポインターの所有権を持つようにこのメソッドを呼び出します。|  
|[CAutoVectorPtr::Detach](../Topic/CAutoVectorPtr::Detach.md)|ポインターの所有権を解放するためにこのメソッドを呼び出します。|  
|[CAutoVectorPtr::Free](../Topic/CAutoVectorPtr::Free.md)|指すにオブジェクトを `CAutoVectorPtr`削除するには、このメソッドを呼び出します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CAutoVectorPtr::operator T \*](../Topic/CAutoVectorPtr::operator%20T%20*.md)|キャスト演算子。|  
|[CAutoVectorPtr::operator \=](../Topic/CAutoVectorPtr::operator%20=.md)|代入演算子です。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAutoVectorPtr::m\_p](../Topic/CAutoVectorPtr::m_p.md)|ポインターのデータ メンバー変数。|  
  
## 解説  
 このクラスは自動的にリソースを解放することによって、範囲からメモリ リークする場合に対して保護するスマート ポインターを作成および管理するためのメソッドを提供します。  `CAutoVectorPtr` は `CAutoPtr`に似ていますが、その `CAutoVectorPtr` である唯一の違い使用 [vector new&#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md) と [vector delete&#91;&#93;](../Topic/operator%20delete\(%3Cnew%3E\).md) C\+\+ **new** と **delete** 演算子ではなくメモリの割り当てと解放します。  `CAutoVectorPtr` のコレクション クラスが必要な場合 [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) を参照してください。  
  
 スマート ポインター クラスの使用例については [CAutoPtr](../../atl/reference/cautoptr-class.md) を参照してください。  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 参照  
 [CAutoPtr クラス](../../atl/reference/cautoptr-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)