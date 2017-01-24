---
title: "CComObject クラス | Microsoft Docs"
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
  - "ATL.CComObject<Base>"
  - "ATL::CComObject"
  - "ATL::CComObject<Base>"
  - "ATL.CComObject"
  - "CComObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObject クラス"
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComObject クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、非集約オブジェクトの **IUnknown** を実装します。  
  
## 構文  
  
```  
  
      template<  
   class Base   
>  
class CComObject :  
   public Base  
```  
  
#### パラメーター  
 `Base`  
 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) か [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から、または他のインターフェイスからクラスが派生したオブジェクトでサポートする必要があります。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComObject::CComObject](../Topic/CComObject::CComObject.md)|コンストラクターです。|  
|[CComObject::~CComObject](../Topic/CComObject::~CComObject.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComObject::AddRef](../Topic/CComObject::AddRef.md)|オブジェクトの参照カウントをインクリメントします。|  
|[CComObject::CreateInstance](../Topic/CComObject::CreateInstance.md)|\(静的関数\) `CComObject` に新しいオブジェクトを作成します。|  
|[CComObject::QueryInterface](../Topic/CComObject::QueryInterface.md)|要求されたインターフェイスへのポインターを取得します。|  
|[CComObject::Release](../Topic/CComObject::Release.md)|オブジェクトの参照カウントをデクリメントします。|  
  
## 解説  
 非集約オブジェクトのを実装します`CComObject`[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)。  ただし、`QueryInterface`、`AddRef`と **\[リリース\]** の呼び出しは `CComObjectRootEx`に転送されます。  
  
 `CComObject`の使用方法の詳細については、" " [ATL COM オブジェクトの基本](../../atl/fundamentals-of-atl-com-objects.md)を参照してください。  
  
## 継承階層  
 `Base`  
  
 `CComObject`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [CComAggObject クラス](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)   
 [DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)   
 [クラスの概要](../../atl/atl-class-overview.md)