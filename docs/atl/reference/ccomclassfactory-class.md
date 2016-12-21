---
title: "CComClassFactory クラス | Microsoft Docs"
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
  - "ATL.CComClassFactory"
  - "CComClassFactory"
  - "ATL::CComClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactory クラス"
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComClassFactory クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、[IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) インターフェイスを実装します。  
  
## 構文  
  
```  
  
   class CComClassFactory : public IClassFactory,   
public CComObjectRootEx< CComGlobalsThreadModel >  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComClassFactory::CreateInstance](../Topic/CComClassFactory::CreateInstance.md)|指定の CLSID を持つオブジェクトを作成します。|  
|[CComClassFactory::LockServer](../Topic/CComClassFactory::LockServer.md)|メモリのクラス ファクトリをロックします。|  
  
## 解説  
 `CComClassFactory` は、特定の CLSID のオブジェクトを作成するメソッドをロックして、アセンブリに加え、新しいオブジェクトがより迅速に作成するためにメモリのクラス ファクトリを [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) のインターフェイスを実装します。  **IClassFactory** は、システム レジストリに登録し、クラスに CLSID に割り当てるかに実装する必要があります。  
  
 ATL オブジェクトは [CComCoClass](../Topic/CComCoClass%20Class.md)から派生させて、通常はクラス ファクトリを取得します。  既定のクラス ファクトリとして `CComClassFactory` を宣言するこのクラスでは、マクロ [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md)が含まれています。  既定の名前をオーバーライドするには、クラス定義で `DECLARE_CLASSFACTORY`*XXX* のマクロの 1 つが指定します。  たとえば、[DECLARE\_CLASSFACTORY\_EX](../Topic/DECLARE_CLASSFACTORY_EX.md) のマクロは、クラス ファクトリ クラスに対して指定を使用します:  
  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/CPP/ccomclassfactory-class_1.h)]  
  
 上記のクラス定義は **CMyClassFactory** がオブジェクトの既定のクラス ファクトリとして使用されることを指定します。  **CMyClassFactory** は `CComClassFactory` から派生し、`CreateInstance`をオーバーライドする必要があります。  
  
 ATL は、クラス ファクトリを宣言する 3 つが他のマクロが用意されています:  
  
-   [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md) は [CComClassFactory2](../Topic/CComClassFactory2%20Class.md)を使用して、ライセンスを通じて作成を制御できます。  
  
-   [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) は [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)を使用して、複数のアパートメントのオブジェクトを作成します。  
  
-   [DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md) は [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)を使用して、[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) の単一のオブジェクトを生成します。  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [クラスの概要](../../atl/atl-class-overview.md)