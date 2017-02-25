---
title: "CAutoPtrArray クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAutoPtrArray<E>"
  - "CAutoPtrArray"
  - "ATL::CAutoPtrArray"
  - "ATL.CAutoPtrArray<E>"
  - "ATL.CAutoPtrArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoPtrArray クラス"
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CAutoPtrArray クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、スマート ポインターの配列を構築するときに役立つメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
typename E  
>  
class CAutoPtrArray : public CAtlArray<  
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
|[CAutoPtrArray::CAutoPtrArray](../Topic/CAutoPtrArray::CAutoPtrArray.md)|コンストラクターです。|  
  
## 解説  
 このクラスは、コンストラクターを提供し、[CAtlArray](../../atl/reference/catlarray-class.md) と [CAutoPtrElementTraits](../Topic/CAutoPtrElementTraits%20Class.md) からスマート ポインターを格納するコレクション クラス オブジェクトの作成を支援するメソッドを取得します。  
  
 詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 継承階層  
 `CAtlArray`  
  
 `CAutoPtrArray`  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [CAtlArray クラス](../../atl/reference/catlarray-class.md)   
 [CAutoPtrElementTraits クラス](../Topic/CAutoPtrElementTraits%20Class.md)   
 [CAutoPtrList クラス](../../atl/reference/cautoptrlist-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)