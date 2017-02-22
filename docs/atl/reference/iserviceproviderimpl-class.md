---
title: "IServiceProviderImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IServiceProviderImpl<T>"
  - "ATL.IServiceProviderImpl<T>"
  - "ATL.IServiceProviderImpl"
  - "ATL::IServiceProviderImpl"
  - "IServiceProviderImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IServiceProvider インターフェイス, ATL の実装"
  - "IServiceProviderImpl クラス"
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# IServiceProviderImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、`IServiceProvider` インターフェイスの既定の実装を提供します。  
  
## 構文  
  
```  
  
      template <  
   class T  
>   
class ATL_NO_VTABLE IServiceProviderImpl :  
   public IServiceProvider  
```  
  
#### パラメーター  
 `T`  
 `IServiceProviderImpl`から派生したクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IServiceProviderImpl::QueryService](../Topic/IServiceProviderImpl::QueryService.md)|作成するか、指定したサービスにアクセス、およびサービスの特定のインターフェイスへのインターフェイス ポインターを返します。|  
  
## 解説  
 `IServiceProvider` のインターフェイスは GUID で指定されたサービスを選択し、サービス要求されたインターフェイスのインターフェイス ポインターを返します。  クラス `IServiceProviderImpl` は、このインターフェイスの既定の実装を提供します。  
  
 **IServiceProviderImpl** は 1 とおりの方法を指定します: [QueryService](../Topic/IServiceProviderImpl::QueryService.md)、作成するか、指定したサービスにアクセス、およびサービスの特定のインターフェイスへのインターフェイス ポインターを返します。  
  
 `IServiceProviderImpl` は [END\_SERVICE\_MAP](../Topic/END_SERVICE_MAP.md)の [BEGIN\_SERVICE\_MAP](../Topic/BEGIN_SERVICE_MAP.md) とまでの一連サービス マップを使用します。  
  
 サービス マップは 2 エントリが含まれます: [SERVICE\_ENTRY](../Topic/SERVICE_ENTRY.md)オブジェクトでサポートされる指定サービス ID \(SID\) を表すと [SERVICE\_ENTRY\_CHAIN](../Topic/SERVICE_ENTRY_CHAIN.md)別のオブジェクトにチェーンするには `QueryService` を呼び出す。  
  
## 継承階層  
 `IServiceProvider`  
  
 `IServiceProviderImpl`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)