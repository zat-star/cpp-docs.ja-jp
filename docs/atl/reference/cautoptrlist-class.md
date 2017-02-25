---
title: "CAutoPtrList クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAutoPtrList"
  - "CAutoPtrList"
  - "ATL.CAutoPtrList"
  - "ATL::CAutoPtrList<E>"
  - "ATL.CAutoPtrList<E>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoPtrList クラス"
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CAutoPtrList クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、スマート ポインターのリストを構築するときに役立つメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
typename E  
>  
class CAutoPtrList : public CAtlList<  
ATL::CAutoPtr< E>,  
CAutoPtrElementTraits< E>  
>  
```  
  
#### パラメーター  
 `E`  
 ポインター型。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAutoPtrList::CAutoPtrList](../Topic/CAutoPtrList::CAutoPtrList.md)|コンストラクターです。|  
  
## 解説  
 このクラスは、コンストラクターを提供し、[CAtlList](../Topic/CAtlList%20Class.md) と [CAutoPtrElementTraits](../Topic/CAutoPtrElementTraits%20Class.md) からスマート ポインターを格納するリスト オブジェクトの作成を支援するメソッドを取得します。  クラス [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) は、配列オブジェクトに似た機能を提供します。  
  
 詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 継承階層  
 [CAtlList](../Topic/CAtlList%20Class.md)  
  
 `CAutoPtrList`  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [CAtlList クラス](../Topic/CAtlList%20Class.md)   
 [CAutoPtrElementTraits クラス](../Topic/CAutoPtrElementTraits%20Class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)