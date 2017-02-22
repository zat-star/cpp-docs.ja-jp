---
title: "CComSafeArrayBound クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComSafeArrayBound"
  - "ATL::CComSafeArrayBound"
  - "CComSafeArrayBound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSafeArrayBound クラス"
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComSafeArrayBound クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは [SAFEARRAYBOUND](http://msdn.microsoft.com/ja-jp/303a9bdb-71d6-4f14-8747-84cf84936c6d) の構造体のラッパー クラスです。  
  
## 構文  
  
```  
  
class CComSafeArrayBound : public SAFEARRAYBOUND  
  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[CComSafeArrayBound](../Topic/CComSafeArrayBound::CComSafeArrayBound.md)|コンストラクターです。|  
|[GetCount](../Topic/CComSafeArrayBound::GetCount.md)|要素の数を返すには、このメソッドを呼び出します。|  
|[GetLowerBound](../Topic/CComSafeArrayBound::GetLowerBound.md)|下限を返すには、このメソッドを呼び出します。|  
|[GetUpperBound](../Topic/CComSafeArrayBound::GetUpperBound.md)|上限を返すには、このメソッドを呼び出します。|  
|[SetCount](../Topic/CComSafeArrayBound::SetCount.md)|要素の数を設定するには、このメソッドを呼び出します。|  
|[SetLowerBound](../Topic/CComSafeArrayBound::SetLowerBound.md)|下限を設定するには、このメソッドを呼び出します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../Topic/CComSafeArrayBound::operator%20=.md)|新しい値に `CComSafeArrayBound` を設定します。|  
  
## 解説  
 このクラスは [CComSafeArray](../Topic/CComSafeArray%20Class.md)で使用される **SAFEARRAYBOUND** の構造体のラッパー クラスです。  これは、照会するメソッドを提供し、`CComSafeArray` の単一の次元の上限と下限を設定およびコンテナー要素の数を取得します。  `CComSafeArray` の多次元オブジェクトは `CComSafeArrayBound` のオブジェクト、各次元の 1 の配列を使用します。  したがって、[GetCount](../Topic/CComSafeArrayBound::GetCount.md)などのメソッドを使用する場合は、このメソッドが多次元配列の要素の総数を返さないことに注意してください。  
  
 **ヘッダー :** atlsafe.h  
  
## 必要条件  
 **ヘッダー :** atlsafe.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)