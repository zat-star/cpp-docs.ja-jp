---
title: "CElementTraitsBase クラス | Microsoft Docs"
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
  - "CElementTraitsBase"
  - "ATL::CElementTraitsBase"
  - "ATL.CElementTraitsBase<T>"
  - "ATL::CElementTraitsBase<T>"
  - "ATL.CElementTraitsBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CElementTraitsBase クラス"
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CElementTraitsBase クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、コレクション クラス用の既定のコピー メソッドと移動メソッドが用意されています。  
  
## 構文  
  
```  
  
      template<  
   typename T  
>  
class CElementTraitsBase  
```  
  
#### パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[CElementTraitsBase::INARGTYPE](../Topic/CElementTraitsBase::INARGTYPE.md)|コレクション クラス オブジェクトに要素を追加するために使用するデータ型。|  
|[CElementTraitsBase::OUTARGTYPE](../Topic/CElementTraitsBase::OUTARGTYPE.md)|コレクション クラス オブジェクトから要素を取得するために使用するデータ型。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CElementTraitsBase::CopyElements](../Topic/CElementTraitsBase::CopyElements.md)|コレクション クラス オブジェクトに格納されている要素をコピーする場合に、このメソッドを呼び出します。|  
|[CElementTraitsBase::RelocateElements](../Topic/CElementTraitsBase::RelocateElements.md)|コレクション クラス オブジェクトに格納されている要素を転送する場合に、このメソッドを呼び出します。|  
  
## 解説  
 この基本クラスはコピー メソッドを定義し、コレクション再配置の要素です。  これは、クラス [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)、[CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)と [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)によって使用されます。  
  
 詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)