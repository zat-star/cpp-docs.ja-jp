---
title: "CComAutoCriticalSection クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComAutoCriticalSection"
  - "ATL::CComAutoCriticalSection"
  - "CComAutoCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAutoCriticalSection クラス"
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComAutoCriticalSection クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComAutoCriticalSection` は、クリティカル セクション オブジェクトの所有権を取得および解放するメソッドを提供します。  
  
## 構文  
  
```  
  
class CComAutoCriticalSection : public CComCriticalSection  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComAutoCriticalSection::CComAutoCriticalSection](../Topic/CComAutoCriticalSection::CComAutoCriticalSection.md)|コンストラクターです。|  
|[CComAutoCriticalSection::~CComAutoCriticalSection](../Topic/CComAutoCriticalSection::~CComAutoCriticalSection.md)|デストラクターです。|  
  
## 解説  
 `CComAutoCriticalSection` は `CComAutoCriticalSection` が自動的にコンストラクターのクリティカル セクション オブジェクトを初期化する以外に似ています [CComCriticalSection](../Topic/CComCriticalSection%20Class.md)を基準に並べ替える。  
  
 通常、`typedef` の名前 [AutoCriticalSection](../Topic/CComMultiThreadModel::AutoCriticalSection.md)によって `CComAutoCriticalSection` を使用します。  [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) が使用されている場合に、この名前参照 `CComAutoCriticalSection`。  
  
 [CComCriticalSection](../Topic/CComCriticalSection%20Class.md) から `Init` と `Term` のメソッドは、このクラスを使用する場合は利用できません。  
  
## 継承階層  
 [CComCriticalSection](../Topic/CComCriticalSection%20Class.md)  
  
 `CComAutoCriticalSection`  
  
## 必要条件  
 **Header:** atlcore.h  
  
## 参照  
 [CComFakeCriticalSection クラス](../../atl/reference/ccomfakecriticalsection-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComCriticalSection クラス](../Topic/CComCriticalSection%20Class.md)