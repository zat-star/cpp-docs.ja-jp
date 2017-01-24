---
title: "CComApartment クラス | Microsoft Docs"
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
  - "ATL::CComApartment"
  - "CComApartment"
  - "ATL.CComApartment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アパートメント (ATL EXE モジュールの)"
  - "CComApartment クラス"
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComApartment クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、スレッドがプールされている EXE モジュールのアパートメントを管理するためのサポートを提供します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CComApartment  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComApartment::CComApartment](../Topic/CComApartment::CComApartment.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComApartment::Apartment](../Topic/CComApartment::Apartment.md)|スレッドの開始アドレスをマークします。|  
|[CComApartment::GetLockCount](../Topic/CComApartment::GetLockCount.md)|スレッドの現在のロック カウントを返します。|  
|[CComApartment::Lock](../Topic/CComApartment::Lock.md)|スレッドのロック カウントをインクリメントします。|  
|[CComApartment::Unlock](../Topic/CComApartment::Unlock.md)|スレッドのロック カウントをデクリメントします。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CComApartment::m\_dwThreadID](../Topic/CComApartment::m_dwThreadID.md)|スレッド識別子が含まれます。|  
|[CComApartment::m\_hThread](../Topic/CComApartment::m_hThread.md)|スレッドのハンドルが含まれます。|  
|[CComApartment::m\_nLockCnt](../Topic/CComApartment::m_nLockCnt.md)|スレッドの現在のロックの数。|  
  
## 解説  
 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) によって`CComApartment` がスレッド プールされた EXE モジュールのアパートメントを管理するために使用されます。  `CComApartment` はスレッドでロック カウントをインクリメントおよびデクリメントするためのメソッドを提供します。  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)