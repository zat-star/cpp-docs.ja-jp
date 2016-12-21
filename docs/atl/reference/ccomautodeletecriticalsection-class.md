---
title: "CComAutoDeleteCriticalSection クラス | Microsoft Docs"
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
  - "ATL.CComAutoDeleteCriticalSection"
  - "CComAutoDeleteCriticalSection"
  - "ATL::CComAutoDeleteCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAutoDeleteCriticalSection クラス"
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComAutoDeleteCriticalSection クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、クリティカル セクション オブジェクトの所有権を取得および解放するためのメソッドが用意されています。  
  
## 構文  
  
```  
  
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection  
  
```  
  
## 解説  
 `CComAutoDeleteCriticalSection` [CComSafeDeleteCriticalSection](../Topic/CComSafeDeleteCriticalSection%20Class.md)はクラスから派生します。  ただし、`CComAutoDeleteCriticalSection` が発生するメモリのクリーンアップを強制的 `private` のアクセス、このクラスのインスタンスがスコープ外になるか、メモリから明示的に削除されたときにのみ [&#91;用語&#93;](../Topic/CComSafeDeleteCriticalSection::Term.md) のメソッドをオーバーライドします。  
  
 このクラスは、基本クラスに対して追加のメソッドはありません。  クリティカル セクションのヘルパー クラスの詳細については [CComSafeDeleteCriticalSection](../Topic/CComSafeDeleteCriticalSection%20Class.md) と [CComCriticalSection](../Topic/CComCriticalSection%20Class.md) を参照してください。  
  
## 継承階層  
 [CComCriticalSection](../Topic/CComCriticalSection%20Class.md)  
  
 [CComSafeDeleteCriticalSection](../Topic/CComSafeDeleteCriticalSection%20Class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## 必要条件  
 **Header:** atlcore.h  
  
## 参照  
 [CComSafeDeleteCriticalSection クラス](../Topic/CComSafeDeleteCriticalSection%20Class.md)   
 [CComCriticalSection クラス](../Topic/CComCriticalSection%20Class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)