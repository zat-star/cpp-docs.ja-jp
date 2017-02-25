---
title: "CComEnumOnSTL クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComEnumOnSTL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnumOnSTL クラス"
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComEnumOnSTL クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、STL コレクションに基づいた COM 列挙子オブジェクトを定義します。  
  
## 構文  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class CollType,  
   class ThreadModel = CComObjectThreadModel  
>  
class ATL_NO_VTABLE CComEnumOnSTL :  
   public IEnumOnSTLImpl<Base, piid, T, Copy, CollType>,  
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
 [コピー ポリシー](../Topic/ATL%20Copy%20Policy%20Classes.md) のクラス。  
  
 `CollType`  
 STL コンテナー クラス。  
  
## 解説  
 `CComEnumOnSTL` は、STL コレクションに基づいた COM 列挙子オブジェクトを定義します。  このクラスは、単独でまたは [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)とともに使用できます。  このクラスを使用する一般的な手順を次説明します。  詳細については、[ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)を参照してください。  
  
## ICollectionOnSTLImpl のこのクラスを使用するには:  
  
-   `typedef` このクラスの特殊化。  
  
-   `ICollectionOnSTLImpl`の特殊化で最終的なテンプレート引数として `typedef` を使用します。  
  
 例については [ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md) を参照してください。  
  
## このクラスを ICollectionOnSTLImpl とは関係なく使用するには:  
  
-   `typedef` このクラスの特殊化。  
  
-   `CComObject`の特殊化でテンプレート引数として `typedef` を使用します。  
  
-   `CComObject` の特化型のインスタンスを作成します。  
  
-   [IEnumOnSTLImpl::Init](../Topic/IEnumOnSTLImpl::Init.md)を呼び出して、列挙子オブジェクトを初期化します。  
  
-   クライアントに列挙子インターフェイスを返します。  
  
## 継承階層  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)  
  
 `CComEnumOnSTL`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 使用例  
 以下のコードは、列挙子オブジェクトの作成と初期化を処理するジェネリック関数が用意されています:  
  
 [!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/CPP/ccomenumonstl-class_1.h)]  
  
 このテンプレート関数は、次に示すように、コレクション インターフェイスの `_NewEnum` のプロパティを実装するために使用できます:  
  
 [!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/CPP/ccomenumonstl-class_2.h)]  
  
 **IEnumVariant** のインターフェイスで `CComVariant`、のベクターを公開するこのコードは `CComEnumOnSTL` の `typedef` を作成します。  **CVariantCollection** のクラスはこの型の列挙子オブジェクトを使用するに **CreateSTLEnumerator** を単純に特化します。  
  
## 参照  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)   
 [ATLCollections サンプル: ICollectionOnSTLImpl、CComEnumOnSTL、およびカスタム コピー ポリシー クラスを示します](../../top/visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComObjectThreadModel](../Topic/CComObjectThreadModel.md)   
 [IEnumOnSTLImpl クラス](../../atl/reference/ienumonstlimpl-class.md)