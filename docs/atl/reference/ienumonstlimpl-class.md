---
title: "IEnumOnSTLImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IEnumOnSTLImpl"
  - "ATL.IEnumOnSTLImpl"
  - "ATL::IEnumOnSTLImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IEnumOnSTLImpl クラス"
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IEnumOnSTLImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、STL コレクションに基づいた列挙子インターフェイスを定義します。  
  
## 構文  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class CollType  
>  
class ATL_NO_VTABLE IEnumOnSTLImpl :  
   public Base  
```  
  
#### パラメーター  
 `Base`  
 COM 列挙子 \([IEnumXXXX](https://msdn.microsoft.com/en-us/library/ms680089.aspx)\) インターフェイス。  
  
 `piid`  
 列挙子インターフェイスのインターフェイス ID へのポインター。  
  
 `T`  
 列挙子インターフェイスによって公開される項目の種類。  
  
 `Copy`  
 [コピー ポリシー クラス](../Topic/ATL%20Copy%20Policy%20Classes.md)。  
  
 `CollType`  
 STL コンテナー クラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IEnumOnSTLImpl::Clone](../Topic/IEnumOnSTLImpl::Clone.md)|[IEnumXXXX::Clone](https://msdn.microsoft.com/en-us/library/ms690336.aspx) の実装。|  
|[IEnumOnSTLImpl::Init](../Topic/IEnumOnSTLImpl::Init.md)|列挙子が初期化されます。|  
|[IEnumOnSTLImpl::Next](../Topic/IEnumOnSTLImpl::Next.md)|[IEnumXXXX::Next](https://msdn.microsoft.com/en-us/library/ms695273.aspx)の実装。|  
|[IEnumOnSTLImpl::Reset](../Topic/IEnumOnSTLImpl::Reset.md)|[IEnumXXXX::Reset](https://msdn.microsoft.com/en-us/library/ms693414.aspx)の実装。|  
|[IEnumOnSTLImpl::Skip](../Topic/IEnumOnSTLImpl::Skip.md)|[IEnumXXXX::Skip](https://msdn.microsoft.com/en-us/library/ms690392.aspx)の実装。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[IEnumOnSTLImpl::m\_iter](../Topic/IEnumOnSTLImpl::m_iter.md)|コレクション内の列挙子の現在の位置を表す反復子。|  
|[IEnumOnSTLImpl::m\_pcollection](../Topic/IEnumOnSTLImpl::m_pcollection.md)|列挙する項目を保持し、STL コンテナーへのポインター。|  
|[IEnumOnSTLImpl::m\_spUnk](../Topic/IEnumOnSTLImpl::m_spUnk.md)|コレクションを指定するオブジェクトの **IUnknown** のポインター。|  
  
## 解説  
 `IEnumOnSTLImpl` が列挙される項目が STL 互換性のあるコンテナーに格納されている COM 列挙子インターフェイスの実装を提供します。  このクラスは、配列に基づいて列挙子インターフェイスの実装を提供する [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) のクラスに似ています。  
  
> [!NOTE]
>  `CComEnumImpl` と `IEnumOnSTLImpl`の違いの詳細については [CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md) を参照してください。  
  
 通常、このインターフェイスの実装から派生することで、独自の列挙子クラスを作成する必要はありません。  STL コンテナーに基づいて ATL 指定した列挙子を使用する場合は [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)のインスタンスを作成または [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)から派生することで列挙子を返すコレクションのクラスを作成するために一般的です。  
  
 ただし、\(たとえば、列挙子インターフェイスの追加、インターフェイスを公開する 1 人\) カスタム列挙子を提供する必要がある場合、このクラスから取得できます。  独自の実装を提供するに [&#91;クローン&#93;](../Topic/IEnumOnSTLImpl::Clone.md) のメソッドをオーバーライドする必要がある場合は、この場合によく発生します。  
  
## 継承階層  
 `Base`  
  
 `IEnumOnSTLImpl`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)