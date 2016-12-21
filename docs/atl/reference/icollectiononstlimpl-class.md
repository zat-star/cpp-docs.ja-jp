---
title: "ICollectionOnSTLImpl クラス | Microsoft Docs"
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
  - "ATL.ICollectionOnSTLImpl"
  - "ATL::ICollectionOnSTLImpl"
  - "ICollectionOnSTLImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICollectionOnSTLImpl クラス"
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICollectionOnSTLImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、コレクション クラスで使用するメソッドが用意されています。  
  
## 構文  
  
```  
  
      template <  
   class T,  
   class CollType,  
   class ItemType,  
   class CopyItem,  
   class EnumType  
>  
class ICollectionOnSTLImpl :  
   public T  
```  
  
#### パラメーター  
 `T`  
 COM コレクションのインターフェイス。  
  
 `CollType`  
 STL コンテナー クラス。  
  
 *ItemType*  
 コンテナーのインターフェイスで公開されている項目の種類。  
  
 *CopyItem*  
 [コピー ポリシー クラス](../Topic/ATL%20Copy%20Policy%20Classes.md)。  
  
 *EnumType*  
 [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)と互換性のある列挙子のクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[ICollectionOnSTLImpl::get\_\_NewEnum](../Topic/ICollectionOnSTLImpl::get__NewEnum.md)|コレクションの列挙子オブジェクトを返します。|  
|[ICollectionOnSTLImpl::get\_Count](../Topic/ICollectionOnSTLImpl::get_Count.md)|コレクションの要素数を返します。|  
|[ICollectionOnSTLImpl::get\_Item](../Topic/ICollectionOnSTLImpl::get_Item.md)|コレクションから要求された項目を返します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[ICollectionOnSTLImpl::m\_coll](../Topic/ICollectionOnSTLImpl::m_coll.md)|コレクションで表されるアイテムを保持します。|  
  
## 解説  
 このクラスには、コレクション インターフェイスの 3 種類のメソッドを実装します: [get\_Count](../Topic/ICollectionOnSTLImpl::get_Count.md)、[get\_Item](../Topic/ICollectionOnSTLImpl::get_Item.md)と [get\_\_NewEnum](../Topic/ICollectionOnSTLImpl::get__NewEnum.md)。  
  
 このクラスを使用するには、次の手順に従います。  
  
-   \(または\) 借用、を実装するコレクションのインターフェイスを定義します。  
  
-   `ICollectionOnSTLImpl` の特殊化からクラスを基づいてこのコレクションのインターフェイスに取得します。  
  
-   `ICollectionOnSTLImpl`で処理されないコレクション インターフェイスのメソッドを実装するために派生クラスを使用します。  
  
> [!NOTE]
>  コレクションのインターフェイスをデュアル インターフェイス、ATL に `IDispatch` のメソッドの実装を提供する場合は、最初のテンプレート パラメーターとして `ICollectionOnSTLImpl` の特殊化を渡す [IDispatchImpl](../../atl/reference/idispatchimpl-class.md)からクラスを派生します。  
  
-   コレクションに格納する [m\_coll](../Topic/ICollectionOnSTLImpl::m_coll.md) のメンバーに項目を追加します。  
  
 詳細については、[ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)を参照してください。  
  
## 継承階層  
 `T`  
  
 `ICollectionOnSTLImpl`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [ATLCollections sample](../../top/visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)