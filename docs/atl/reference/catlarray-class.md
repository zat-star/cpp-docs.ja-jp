---
title: "CAtlArray クラス | Microsoft Docs"
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
  - "ATL::CAtlArray"
  - "ATL.CAtlArray"
  - "CAtlArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlArray クラス"
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlArray クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、配列オブジェクトを実装します。  
  
## 構文  
  
```  
  
      template<   
   typename E,  
   class ETraits = CElementTraits< E >   
>  
class CAtlArray  
```  
  
#### パラメーター  
 *E*  
 配列に格納されるデータの型。  
  
 *ETraits*  
 要素をコピーまたは移動するときに使用するコード。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[追加](../Topic/CAtlArray::Add.md)|配列オブジェクトに要素を追加するには、このメソッドを呼び出します。|  
|[追加します。](../Topic/CAtlArray::Append.md)|別の最後に 1 二つの配列の内容を追加するには、このメソッドを呼び出します。|  
|[AssertValid](../Topic/CAtlArray::AssertValid.md)|配列オブジェクトが有効であることを確認するためにこのメソッドを呼び出します。|  
|[CAtlArray](../Topic/CAtlArray::CAtlArray.md)|コンストラクターです。|  
|[~CAtlArray](../Topic/CAtlArray::~CAtlArray.md)|デストラクターです。|  
|[コピー](../Topic/CAtlArray::Copy.md)|別の型に 1 個の配列の要素をコピーする場合は、このメソッドを呼び出します。|  
|[FreeExtra](../Topic/CAtlArray::FreeExtra.md)|空の配列から要素を削除するには、このメソッドを呼び出します。|  
|[GetAt](../Topic/CAtlArray::GetAt.md)|配列オブジェクトから単一の要素を取得するときにこのメソッドを呼び出します。|  
|[GetCount](../Topic/CAtlArray::GetCount.md)|配列に格納されている要素の数を返すには、このメソッドを呼び出します。|  
|[GetData](../Topic/CAtlArray::GetData.md)|配列の最初の要素へのポインターを返すには、このメソッドを呼び出します。|  
|[InsertArrayAt](../Topic/CAtlArray::InsertArrayAt.md)|別の型に 1 個の配列を挿入する場合に、このメソッドを呼び出します。|  
|[InsertAt](../Topic/CAtlArray::InsertAt.md)|配列オブジェクトに新しい要素または要素の複数のコピーを挿入する場合に、このメソッドを呼び出します。|  
|[IsEmpty](../Topic/CAtlArray::IsEmpty.md)|配列が空テストするには、このメソッドを呼び出します。|  
|[RemoveAll](../Topic/CAtlArray::RemoveAll.md)|配列オブジェクトからすべての要素を削除するには、このメソッドを呼び出します。|  
|[RemoveAt](../Topic/CAtlArray::RemoveAt.md)|配列から要素を削除するには、このメソッドを呼び出します。|  
|[SetAt](../Topic/CAtlArray::SetAt.md)|配列オブジェクトの要素の値を設定するには、このメソッドを呼び出します。|  
|[SetAtGrow](../Topic/CAtlArray::SetAtGrow.md)|配列を配置する必要に応じて配列オブジェクトの要素の値を設定するには、このメソッドを呼び出します。|  
|[SetCount](../Topic/CAtlArray::SetCount.md)|配列オブジェクトのサイズを設定するには、このメソッドを呼び出します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator &#91;&#93;](../Topic/CAtlArray::operator.md)|配列の要素への参照を返すには、この演算子を呼び出します。|  
  
### Typedef  
  
|||  
|-|-|  
|[INARGTYPE](../Topic/CAtlArray::INARGTYPE.md)|配列に要素を追加するために使用するデータ型。|  
|[OUTARGTYPE](../Topic/CAtlArray::OUTARGTYPE.md)|配列から要素を取得するために使用するデータ型。|  
  
## 解説  
 **CAtlArray**、ユーザー定義型の要素の配列を作成および管理するためのメソッドを提供します。  標準 C の配列に似ていますが、**CAtlArray** のオブジェクトは、必要に応じて動的に縮小し、拡張できます。  新しい要素が追加される場合、位置 0 の配列のインデックスは常にの開始され、上限が修正または配置することを許可できます。  
  
 一部の要素を持つ配列は、ATL のクラス [CSimpleArray](../../atl/reference/csimplearray-class.md) を使用できます。  
  
 **CAtlArray** は、MFC の **CArray** のクラスに密接に関連し、MFC プロジェクトでシリアル化のサポートなしで、とはいえ動作します。  
  
 詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [MMXSwarm サンプル](../../top/visual-cpp-samples.md)   
 [DynamicConsumer サンプル](../../top/visual-cpp-samples.md)   
 [UpdatePV サンプル](../../top/visual-cpp-samples.md)   
 [Marquee サンプル](../../top/visual-cpp-samples.md)   
 [CArray クラス](../../mfc/reference/carray-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)