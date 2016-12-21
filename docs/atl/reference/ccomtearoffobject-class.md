---
title: "CComTearOffObject クラス | Microsoft Docs"
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
  - "ATL::CComTearOffObject<Base>"
  - "ATL::CComTearOffObject"
  - "ATL.CComTearOffObject"
  - "ATL.CComTearOffObject<Base>"
  - "CComTearOffObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComTearOffObject クラス"
  - "ティアオフ インターフェイス"
  - "ティアオフ インターフェイス, ATL"
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComTearOffObject クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、ティアオフ インターフェイスを実装します。  
  
## 構文  
  
```  
  
      template<  
   class Base   
>  
class CComTearOffObject :  
   public Base  
```  
  
#### パラメーター  
 `Base`  
 `CComTearOffObjectBase` から派生したクラスのティアオフ インターフェイス、およびサポートへのティアオフのオブジェクトを関連付けます。  
  
 ATL は 2 段階のティアオフ インターフェイスを実装します。`CComTearOffObjectBase` のメソッドは `CComTearOffObject` は [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)を実行しますが、参照カウントと `QueryInterface`を処理します。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComTearOffObject::CComTearOffObject](../Topic/CComTearOffObject::CComTearOffObject.md)|コンストラクターです。|  
|[CComTearOffObject::~CComTearOffObject](../Topic/CComTearOffObject::~CComTearOffObject.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComTearOffObject::AddRef](../Topic/CComTearOffObject::AddRef.md)|`CComTearOffObject` のオブジェクトの参照カウントをインクリメントします。|  
|[CComTearOffObject::QueryInterface](../Topic/CComTearOffObject::QueryInterface.md)|アプリケーションのティアオフの所有者クラスの要求されたインターフェイスへのポインターを返します。|  
|[CComTearOffObject::Release](../Topic/CComTearOffObject::Release.md)|`CComTearOffObject` のオブジェクトの参照カウントをデクリメントし、破棄します。|  
  
### CComTearOffObjectBase のメソッド  
  
|||  
|-|-|  
|[CComTearOffObjectBase](../Topic/CComTearOffObject::CComTearOffObjectBase.md)|コンストラクターです。|  
  
### CComTearOffObjectBase のデータ メンバー  
  
|||  
|-|-|  
|[m\_pOwner](../Topic/CComTearOffObject::m_pOwner.md)|`CComObject` へのポインターは所有者クラスから派生します。|  
  
## 解説  
 `CComTearOffObject` は、そのインターフェイスが問い合わせを受ける場合にのみのため、ティアオフ インターフェイスをインスタンス化する別のオブジェクト実装します。  ティアオフは、参照カウントがゼロになると削除されます。  通常、ティアオフを使用することはメイン オブジェクトのすべてのインスタンスの vtable ポインターを保存するため、あまり使用されないインターフェイスのティアオフ インターフェイスをビルドします。  
  
 `CComTearOffObjectBase` からティアオフを実装するクラスを取得するには、からすべてのインターフェイス サポートへのティアオフのオブジェクトを取得する。  `CComTearOffObjectBase` は所有者クラスとスレッド モデルでテンプレート化されます。  所有者クラスは、ティアオフが実行されているオブジェクトのクラスです。  スレッド モデルを指定しない場合、既定のスレッド モデルが使用されます。  
  
 アプリケーションのティアオフのクラスには、COM インターフェイス マップを作成する必要があります。  ATL は、ティアオフをインスタンス化する場合、または **CComTearOffObjectCYourTearOffClassCComCachedTearOffObjectCYourTearOffClass**を作成します。  
  
 たとえば、BEEPER サンプルは、`CBeeper2` のクラスは、ティアオフのクラスであり、`CBeeper` のクラスは、所有者クラスです:  
  
 [!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/CPP/ccomtearoffobject-class_1.h)]  
  
## 継承階層  
 `Base`  
  
 `CComTearOffObject`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [CComCachedTearOffObject クラス](../../atl/reference/ccomcachedtearoffobject-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)