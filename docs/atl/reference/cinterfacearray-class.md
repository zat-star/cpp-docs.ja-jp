---
title: "CInterfaceArray クラス | Microsoft Docs"
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
  - "ATL.CInterfaceArray"
  - "CInterfaceArray"
  - "ATL::CInterfaceArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInterfaceArray クラス"
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CInterfaceArray クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、COM インターフェイス ポインターの配列を構築するときに役立つメソッドが用意されています。  
  
## 構文  
  
```  
  
      template<  
   class I,  
   const IID* piid = & __uuidof( I )  
>  
class CInterfaceArray : public CAtlArray<  
   ATL::CComQIPtr< I, piid >,  
   CComQIPtrElementTraits< I, piid >  
>  
```  
  
#### パラメーター  
 `I`  
 COM を格納するポインターの型を指定することを実装します。  
  
 `piid`  
 `I` の IID へのポインター。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CInterfaceArray::CInterfaceArray](../Topic/CInterfaceArray::CInterfaceArray.md)|インターフェイスの配列のコンストラクター。|  
  
## 解説  
 このクラスは、COM インターフェイス ポインターの配列を作成するコンストラクターと派生メソッドを提供します。  リストが要求されると [CInterfaceList](../Topic/CInterfaceList%20Class.md) を使用します。  
  
 詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 継承階層  
 `CAtlArray`  
  
 `CInterfaceArray`  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [CAtlArray クラス](../../atl/reference/catlarray-class.md)   
 [CComQIPtr クラス](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits クラス](../Topic/CComQIPtrElementTraits%20Class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)