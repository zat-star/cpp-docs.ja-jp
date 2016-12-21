---
title: "CComEnumImpl クラス | Microsoft Docs"
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
  - "ATL.CComEnumImpl"
  - "ATL::CComEnumImpl"
  - "CComEnumImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnumImpl クラス"
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComEnumImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、COM 列挙子インターフェイスの実装を提供します。このインターフェイスでは、列挙されるアイテムが配列に格納されます。  
  
## 構文  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy  
>  
class ATL_NO_VTABLE CComEnumImpl :   
   public Base  
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
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComEnumImpl::CComEnumImpl](../Topic/CComEnumImpl::CComEnumImpl.md)|コンストラクターです。|  
|[CComEnumImpl::~CComEnumImpl](../Topic/CComEnumImpl::~CComEnumImpl.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComEnumImpl::Clone](../Topic/CComEnumImpl::Clone.md)|[IEnumXXXX::Clone](https://msdn.microsoft.com/en-us/library/ms690336.aspx) の実装。|  
|[CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md)|列挙子が初期化されます。|  
|[CComEnumImpl::Next](../Topic/CComEnumImpl::Next.md)|[IEnumXXXX::Next](https://msdn.microsoft.com/en-us/library/ms695273.aspx) の実装。|  
|[CComEnumImpl::Reset](../Topic/CComEnumImpl::Reset.md)|[IEnumXXXX::Reset](https://msdn.microsoft.com/en-us/library/ms693414.aspx) の実装。|  
|[CComEnumImpl::Skip](../Topic/CComEnumImpl::Skip.md)|[IEnumXXXX::Skip](https://msdn.microsoft.com/en-us/library/ms690392.aspx) の実装。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CComEnumImpl::m\_begin](../Topic/CComEnumImpl::m_begin.md)|配列の最初の項目へのポインター。|  
|[CComEnumImpl::m\_dwFlags](../Topic/CComEnumImpl::m_dwFlags.md)|`Init`に渡されるコピーのフラグ。|  
|[CComEnumImpl::m\_end](../Topic/CComEnumImpl::m_end.md)|配列の最後の項目を超える位置へのポインターだけ。|  
|[CComEnumImpl::m\_iter](../Topic/CComEnumImpl::m_iter.md)|配列内の現在の項目へのポインター。|  
|[CComEnumImpl::m\_spUnk](../Topic/CComEnumImpl::m_spUnk.md)|列挙されるコレクションを指定するオブジェクトの **IUnknown** のポインター。|  
  
## 解説  
 `CComEnumImpl` が列挙される項目が配列に格納されている COM 列挙子インターフェイスの実装を提供します。  このクラスは、STL コンテナーに基づいて列挙子インターフェイスの実装を提供する `IEnumOnSTLImpl` のクラスに似ています。  
  
> [!NOTE]
>  `CComEnumImpl` と `IEnumOnSTLImpl`の違いの詳細については、[CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md)を参照してください。  
  
 通常、このインターフェイスの実装から派生することで、独自の列挙子クラスを作成する必要はありません。  配列に基づいて ATL 指定した列挙子を使用する場合は [CComEnum](../../atl/reference/ccomenum-class.md)のインスタンスを作成するための共通です。  
  
 ただし、\(たとえば、列挙子インターフェイスの追加、インターフェイスを公開する 1 人\) カスタム列挙子を提供する必要がある場合、このクラスから取得できます。  独自の実装を提供するに [CComEnumImpl::Clone](../Topic/CComEnumImpl::Clone.md) のメソッドをオーバーライドする必要があると、この場合、高くなります。  
  
 詳細については、[ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)を参照してください。  
  
## 継承階層  
 `Base`  
  
 `CComEnumImpl`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [IEnumOnSTLImpl クラス](../../atl/reference/ienumonstlimpl-class.md)   
 [CComEnum クラス](../../atl/reference/ccomenum-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)