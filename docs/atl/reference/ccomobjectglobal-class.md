---
title: "CComObjectGlobal クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComObjectGlobal"
  - "ATL::CComObjectGlobal<Base>"
  - "ATL::CComObjectGlobal"
  - "ATL.CComObjectGlobal"
  - "ATL.CComObjectGlobal<Base>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectGlobal クラス"
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComObjectGlobal クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、`Base` オブジェクトを含むモジュールの参照カウントを管理します。  
  
## 構文  
  
```  
  
      template<  
   class Base   
>  
class CComObjectGlobal :  
   public Base  
```  
  
#### パラメーター  
 `Base`  
 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) か [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から、または他のインターフェイスからクラスが派生したオブジェクトでサポートする必要があります。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComObjectGlobal::CComObjectGlobal](../Topic/CComObjectGlobal::CComObjectGlobal.md)|コンストラクターです。|  
|[CComObjectGlobal::~CComObjectGlobal](../Topic/CComObjectGlobal::~CComObjectGlobal.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComObjectGlobal::AddRef](../Topic/CComObjectGlobal::AddRef.md)|グローバル `AddRef`を実装します。|  
|[CComObjectGlobal::QueryInterface](../Topic/CComObjectGlobal::QueryInterface.md)|グローバル `QueryInterface`を実装します。|  
|[CComObjectGlobal::Release](../Topic/CComObjectGlobal::Release.md)|グローバル **\[リリース\]**を実装します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CComObjectGlobal::m\_hResFinalConstruct](../Topic/CComObjectGlobal::m_hResFinalConstruct.md)|`CComObjectGlobal` のオブジェクトの構築時に返される **HRESULT** が含まれます。|  
  
## 解説  
 `Base` の`CComObjectGlobal` は、オブジェクトを含むモジュールの参照カウントを管理します。  `CComObjectGlobal` は、モジュールが解放されない限り、オブジェクトが削除されないようにします。  は、オブジェクト全体のモジュールの参照カウントがゼロになる場合にのみ削除されます。  
  
 たとえば、`CComObjectGlobal`を使用して、クラス ファクトリは、すべてのクライアントによって共有される共通のグローバルなオブジェクトを保持できます。  
  
## 継承階層  
 `Base`  
  
 `CComObjectGlobal`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [CComObjectStack クラス](../Topic/CComObjectStack%20Class.md)   
 [CComAggObject クラス](../../atl/reference/ccomaggobject-class.md)   
 [CComObject クラス](../../atl/reference/ccomobject-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)