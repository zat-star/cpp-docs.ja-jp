---
title: "CStringElementTraitsI クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CStringElementTraitsI"
  - "CStringElementTraitsI"
  - "ATL.CStringElementTraitsI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringElementTraitsI クラス"
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CStringElementTraitsI クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、コレクション クラス オブジェクトに格納されている文字列に関連する静的関数が用意されています。  [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) と似ていますが、大文字と小文字を区別せずに比較を行います。  
  
## 構文  
  
```  
  
      template<  
   typename T,  
   class CharTraits = CDefaultCharTraits< T::XCHAR >  
>  
class CStringElementTraitsI : public CElementTraitsBase< T >  
```  
  
#### パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[CStringElementTraitsI::INARGTYPE](../Topic/CStringElementTraitsI::INARGTYPE.md)|コレクション クラス オブジェクトに要素を追加するために使用するデータ型。|  
|[CStringElementTraitsI::OUTARGTYPE](../Topic/CStringElementTraitsI::OUTARGTYPE.md)|コレクション クラス オブジェクトから要素を取得するために使用するデータ型。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CStringElementTraitsI::CompareElements](../Topic/CStringElementTraitsI::CompareElements.md)|違いを無視して、等価性を 2 文字列の要素を比較するには、この静的関数を呼び出します。|  
|[CStringElementTraitsI::CompareElementsOrdered](../Topic/CStringElementTraitsI::CompareElementsOrdered.md)|違いを無視して 2 文字列の要素を比較するには、この静的関数を呼び出します。|  
|[CStringElementTraitsI::Hash](../Topic/CStringElementTraitsI::Hash.md)|特定の文字列要素のハッシュ値を計算するには、この静的関数を呼び出します。|  
  
## 解説  
 このクラスは、文字列を比較するとハッシュ値を作成する静的関数を提供します。  これらの関数は、文字列ベースのデータを格納するコレクション クラスを使用する場合に役立ちます。  文字列オブジェクトを参照として処理されるとの場合 [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) を使用します。  
  
 詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 継承階層  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringElementTraitsI`  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [CElementTraitsBase クラス](../../atl/reference/celementtraitsbase-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CStringElementTraits クラス](../../atl/reference/cstringelementtraits-class.md)