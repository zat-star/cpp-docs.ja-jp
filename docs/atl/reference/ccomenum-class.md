---
title: "CComEnum クラス | Microsoft Docs"
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
  - "CComEnum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnum クラス"
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComEnum クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、配列に基づいた COM 列挙子オブジェクトを定義します。  
  
## 構文  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class ThreadModel = CcomObjectThreadModel  
>  
class ATL_NO_VTABLE CComEnum :  
   public CComEnumImpl<Base, piid, T, Copy>,  
   public CComObjectRootEx< ThreadModel >  
```  
  
#### パラメーター  
 `Base`  
 COM 列挙子インターフェイス \([IEnumXXXX](https://msdn.microsoft.com/en-us/library/ms680089.aspx)\)。  
  
 `piid`  
 列挙子インターフェイスのインターフェイス ID へのポインター。  
  
 `T`  
 列挙子インターフェイスによって公開される項目の種類。  
  
 `Copy`  
 同種 [コピー ポリシー クラス](../Topic/ATL%20Copy%20Policy%20Classes.md)。  
  
 `ThreadModel`  
 クラスのスレッド処理モデル。  このパラメーターは、プロジェクトに使用するグローバル オブジェクトのスレッド モデルになります。  
  
## 解説  
 `CComEnum` は、配列に基づいた COM 列挙子オブジェクトを定義します。  STL コンテナーに基づいて列挙子を実装するクラスは、この [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) に似ています。  このクラスを使用する一般的な手順を次説明します。  詳細については、[ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)を参照してください。  
  
## このクラスを使用するには、次の手順に従います。  
  
-   `typedef` このクラスの特殊化。  
  
-   `CComObject`の特殊化でテンプレート引数として `typedef` を使用します。  
  
-   `CComObject` の特化型のインスタンスを作成します。  
  
-   [CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md)を呼び出して、列挙子オブジェクトを初期化します。  
  
-   クライアントに列挙子インターフェイスを返します。  
  
## 継承階層  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 使用例  
 以下のコードは、列挙子オブジェクトを作成および初期化するために、再利用可能な関数を提供します。  
  
 [!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/CPP/ccomenum-class_1.h)]  
  
 このテンプレート関数は、次に示すように、コレクション インターフェイスの `_NewEnum` のプロパティを実装するために使用できます:  
  
 [!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/CPP/ccomenum-class_2.h)]  
  
 **IEnumVariant** のインターフェイスを通じて **VARIANT**、のベクターを公開するこのコードは `CComEnum` の `typedef` を作成します。  **CVariantArrayCollection** のクラスはこの型の列挙子オブジェクトを使用するに **CreateEnumerator** を単純に特化して、必要な引数を渡します。  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](../Topic/CComObjectThreadModel.md)   
 [CComEnumImpl クラス](../../atl/reference/ccomenumimpl-class.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)