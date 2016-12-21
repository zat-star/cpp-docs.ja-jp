---
title: "CStringRefElementTraits クラス | Microsoft Docs"
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
  - "CStringRefElementTraits"
  - "ATL.CStringRefElementTraits"
  - "ATL::CStringRefElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringRefElementTraits クラス"
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringRefElementTraits クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、コレクション クラス オブジェクトに格納されている文字列に関連する静的関数が用意されています。  文字列オブジェクトは参照として処理されます。  
  
## 構文  
  
```  
  
      template<   
   typename T  
>  
class CStringRefElementTraits : public CElementTraitsBase< T >  
```  
  
#### パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CStringRefElementTraits::CompareElements](../Topic/CStringRefElementTraits::CompareElements.md)|等値の 2 文字列の要素を比較するには、この静的関数を呼び出します。|  
|[CStringRefElementTraits::CompareElementsOrdered](../Topic/CStringRefElementTraits::CompareElementsOrdered.md)|2 番目の文字列の要素を比較するには、この静的関数を呼び出します。|  
|[CStringRefElementTraits::Hash](../Topic/CStringRefElementTraits::Hash.md)|特定の文字列要素のハッシュ値を計算するには、この静的関数を呼び出します。|  
  
## 解説  
 このクラスは、文字列を比較するとハッシュ値を作成する静的関数を提供します。  これらの関数は、文字列ベースのデータを格納するコレクション クラスを使用する場合に役立ちます。  [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) と [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)とは異なり、`CStringRefElementTraits` は `CString` の引数を **const CString&** の参照として渡します。  
  
 詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 継承階層  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [CElementTraitsBase クラス](../../atl/reference/celementtraitsbase-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)