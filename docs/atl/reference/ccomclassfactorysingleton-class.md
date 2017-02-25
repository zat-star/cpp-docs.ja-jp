---
title: "CComClassFactorySingleton クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComClassFactorySingleton"
  - "ATL.CComClassFactorySingleton<T>"
  - "ATL::CComClassFactorySingleton"
  - "ATL::CComClassFactorySingleton<T>"
  - "CComClassFactorySingleton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactorySingleton クラス"
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComClassFactorySingleton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、[CComClassFactory](../../atl/reference/ccomclassfactory-class.md) から派生します。また、[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) を使用して単一のオブジェクトを生成します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
class T  
>  
class CComClassFactorySingleton :  
public CComClassFactory  
```  
  
#### パラメーター  
 `T`  
 自分のクラス。  
  
 `CComClassFactorySingleton` は [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) から派生し、一つのオブジェクトの構築に [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) を使用します。  `CreateInstance` のメソッドを呼び出すたびに、インターフェイス ポインターのこのオブジェクトを照会します。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComClassFactorySingleton::CreateInstance](../Topic/CComClassFactorySingleton::CreateInstance.md)|インターフェイス ポインターの `m_spObj` を照会します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CComClassFactorySingleton::m\_spObj](../Topic/CComClassFactorySingleton::m_spObj.md)|`CComClassFactorySingleton`で構築 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) のオブジェクト。|  
  
## 解説  
 ATL オブジェクトは [CComCoClass](../Topic/CComCoClass%20Class.md)から派生させて、通常はクラス ファクトリを取得します。  既定のクラス ファクトリとして `CComClassFactory` を宣言するこのクラスでは、マクロ [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md)が含まれています。  `CComClassFactorySingleton`を使用するには、オブジェクトのクラス定義に [DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md) のマクロを指定します。  以下はその例です。  
  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/CPP/ccomclassfactorysingleton-class_1.h)]  
  
## 継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)  
  
 `CComClassFactorySingleton`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 クラス](../Topic/CComClassFactory2%20Class.md)   
 [CComClassFactoryAutoThread クラス](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [クラスの概要](../../atl/atl-class-overview.md)