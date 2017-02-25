---
title: "CComObjectRoot クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComObjectRoot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectRoot クラス"
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CComObjectRoot クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) のこの typedef は、サーバーの既定のスレッド化モデルでテンプレート化されます。  
  
## 構文  
  
```  
  
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;  
  
```  
  
## 解説  
 `CComObjectRoot` では、サーバーの既定のスレッド モデルで [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) の `typedef` テンプレート化されます。  したがって [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) は [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) か [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)を参照します。  
  
 非集約オブジェクトの`CComObjectRootEx` ハンドルのオブジェクトの参照カウントを管理します。  これは、のオブジェクトを集約する場合は、オブジェクトを集約する保持し、外側の不明にポインターを保持するオブジェクトの参照カウントを示します。  集約オブジェクトに対して構成要素へのオブジェクトの内部エラーの処理に、`CComObjectRootEx` のメソッドが使用でき、内側のインターフェイスが解放される内部オブジェクトまたは保護するために削除された場合、削除の外部オブジェクトが。  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [CComObjectRootEx Class Members](http://msdn.microsoft.com/ja-jp/e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComAggObject クラス](../../atl/reference/ccomaggobject-class.md)   
 [CComObject クラス](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)