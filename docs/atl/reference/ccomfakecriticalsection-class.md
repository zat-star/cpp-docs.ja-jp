---
title: "CComFakeCriticalSection クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComFakeCriticalSection"
  - "CComFakeCriticalSection"
  - "ATL::CComFakeCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComFakeCriticalSection クラス"
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComFakeCriticalSection クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには [CComCriticalSection](../Topic/CComCriticalSection%20Class.md) と同じメソッドが用意されていますが、クリティカル セクションは用意されていません。  
  
## 構文  
  
```  
  
class CComFakeCriticalSection  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComFakeCriticalSection::Init](../Topic/CComFakeCriticalSection::Init.md)|クリティカル セクションがないため、何も行われません。|  
|[CComFakeCriticalSection::Lock](../Topic/CComFakeCriticalSection::Lock.md)|クリティカル セクションがないため、何も行われません。|  
|[CComFakeCriticalSection::Term](../Topic/CComFakeCriticalSection::Term.md)|クリティカル セクションがないため、何も行われません。|  
|[CComFakeCriticalSection::Unlock](../Topic/CComFakeCriticalSection::Unlock.md)|クリティカル セクションがないため、何も行われません。|  
  
## 解説  
 `CComFakeCriticalSection` は [CComCriticalSection](../Topic/CComCriticalSection%20Class.md)にあるメソッドを反映します。  ただし、`CComFakeCriticalSection` は、クリティカル セクションがありません; したがって、メソッドは何も実行しません。  
  
 通常、`typedef` の名前で `CComFakeCriticalSection` を `AutoCriticalSection`、または `CriticalSection`使用します。  [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) か [CComMultiThreadModelNoCS](../Topic/CComMultiThreadModelNoCS%20Class.md)を使用する場合は、`typedef` の両方の名前参照 `CComFakeCriticalSection`。  [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)を使用する場合は、[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) と `CComCriticalSection`をそれぞれ参照します。  
  
## 必要条件  
 **ヘッダー :** atlcore.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)