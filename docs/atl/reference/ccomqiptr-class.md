---
title: "CComQIPtr クラス | Microsoft Docs"
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
  - "ATL.CComQIPtr"
  - "ATL::CComQIPtr"
  - "CComQIPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComQIPtr クラス"
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComQIPtr クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

COM インターフェイス ポインターを管理するためのスマート ポインター クラスです。  
  
## 構文  
  
```  
  
      template<  
   class T,  
   const IID* piid = &__uuidof(T)  
>  
class CComQIPtr: public CComPtr<T>  
```  
  
#### パラメーター  
 `T`  
 COM を格納するポインターの型を指定することを実装します。  
  
 `piid`  
 `T` の IID へのポインター。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)|コンストラクターです。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CComQIPtr::operator \=](../Topic/CComQIPtr::operator%20=.md)|メンバーのポインターにポインターを割り当てます。|  
  
## 解説  
 ATL を使用 `CComQIPtr` と [CComPtr](../../atl/reference/ccomptr-class.md) は、COM を管理する [CComPtrBase](../../atl/reference/ccomptrbase-class.md)からインターフェイス ポインターを取得します。  どちらのクラス `AddRef` と **\[リリース\]**の呼び出しによって、参照カウントを実行します。  オーバーロードされた演算子は、ポインター操作を行います。  
  
## 継承階層  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 [CComPtr](../../atl/reference/ccomptr-class.md)  
  
 `CComQIPtr`  
  
## 必要条件  
 ヘッダー : atlcomcli.h  
  
## 参照  
 [CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)   
 [CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)   
 [CComPtrBase クラス](../../atl/reference/ccomptrbase-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComQIPtrElementTraits クラス](../Topic/CComQIPtrElementTraits%20Class.md)