---
title: "CComClassFactoryAutoThread クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComClassFactoryAutoThread"
  - "ATL.CComClassFactoryAutoThread"
  - "CComClassFactoryAutoThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactoryAutoThread クラス"
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComClassFactoryAutoThread クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) のインターフェイスを実装し、オブジェクトが複数のアパートメントで作成できます。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      class CComClassFactoryAutoThread : public IClassFactory,   
public CComObjectRootEx< CComGlobalsThreadModel >  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComClassFactoryAutoThread::CreateInstance](../Topic/CComClassFactoryAutoThread::CreateInstance.md)|指定の CLSID を持つオブジェクトを作成します。|  
|[CComClassFactoryAutoThread::LockServer](../Topic/CComClassFactoryAutoThread::LockServer.md)|メモリのクラス ファクトリをロックします。|  
  
## 解説  
 `CComClassFactoryAutoThread` は [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)に似ていますが、オブジェクトが複数のアパートメントで作成できます。  このサポートを利用するには、[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)から EXE のモジュールを取得します。  
  
 ATL オブジェクトは [CComCoClass](../Topic/CComCoClass%20Class.md)から派生させて、通常はクラス ファクトリを取得します。  既定のクラス ファクトリとして [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) を宣言するこのクラスでは、マクロ [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md)が含まれています。  `CComClassFactoryAutoThread`を使用するには、オブジェクトのクラス定義に [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) のマクロを指定します。  例:  
  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/CPP/ccomclassfactoryautothread-class_1.h)]  
  
## 継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 `CComClassFactoryAutoThread`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 クラス](../Topic/CComClassFactory2%20Class.md)   
 [CComClassFactorySingleton クラス](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [クラスの概要](../../atl/atl-class-overview.md)