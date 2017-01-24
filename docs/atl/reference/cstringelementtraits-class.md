---
title: "CStringElementTraits クラス | Microsoft Docs"
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
  - "ATL.CStringElementTraits<T>"
  - "ATL::CStringElementTraits<T>"
  - "CStringElementTraits"
  - "ATL.CStringElementTraits"
  - "ATL::CStringElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringElementTraits クラス"
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringElementTraits クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、`CString` オブジェクトを格納するコレクション クラスで使用する静的関数が用意されています。  
  
## 構文  
  
```  
  
      template<  
   typename T   
>  
class CStringElementTraits  
```  
  
#### パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[CStringElementTraits::INARGTYPE](../Topic/CStringElementTraits::INARGTYPE.md)|コレクション クラス オブジェクトに要素を追加するために使用するデータ型。|  
|[CStringElementTraits::OUTARGTYPE](../Topic/CStringElementTraits::OUTARGTYPE.md)|コレクション クラス オブジェクトから要素を取得するために使用するデータ型。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CStringElementTraits::CompareElements](../Topic/CStringElementTraits::CompareElements.md)|\(静的\) 等値の 2 文字列の要素を比較するには、この関数を呼び出します。|  
|[CStringElementTraits::CompareElementsOrdered](../Topic/CStringElementTraits::CompareElementsOrdered.md)|\(静的\) 2 文字列の要素を比較するには、この関数を呼び出します。|  
|[CStringElementTraits::CopyElements](../Topic/CStringElementTraits::CopyElements.md)|\(静的\) コレクション クラス オブジェクトに格納されている `CString` の要素をコピーするには、この関数を呼び出します。|  
|[CStringElementTraits::Hash](../Topic/CStringElementTraits::Hash.md)|\(静的\) 特定の文字列要素のハッシュ値を計算するには、この関数を呼び出します。|  
|[CStringElementTraits::RelocateElements](../Topic/CStringElementTraits::RelocateElements.md)|\(静的\) コレクション クラス オブジェクトに格納されている `CString` の要素を移動するには、この関数を呼び出します。|  
  
## 解説  
 このクラスは、文字列をコピー、移動、および比較するとハッシュ値を作成する静的関数を提供します。  これらの関数は、文字列ベースのデータを格納するコレクション クラスを使用する場合に役立ちます。  大文字小文字を区別しない比較が必要な場合 [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) を使用します。  文字列オブジェクトを参照として処理される場合 [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) を使用します。  
  
 詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 必要条件  
 **ヘッダー:** cstringt.h  
  
## 参照  
 [CElementTraitsBase クラス](../../atl/reference/celementtraitsbase-class.md)   
 [CStringElementTraitsI クラス](../../atl/reference/cstringelementtraitsi-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)