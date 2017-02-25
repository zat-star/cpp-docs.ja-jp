---
title: "CHandle クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CHandle"
  - "ATL::CHandle"
  - "CHandle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHandle クラス"
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CHandle クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、ハンドル オブジェクトを作成および使用するためのメソッドが用意されています。  
  
## 構文  
  
```  
  
class CHandle  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CHandle::CHandle](../Topic/CHandle::CHandle.md)|コンストラクターです。|  
|[CHandle::~CHandle](../Topic/CHandle::~CHandle.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CHandle::Attach](../Topic/CHandle::Attach.md)|既存のハンドルへの `CHandle` のオブジェクトをアタッチするには、このメソッドを呼び出します。|  
|[CHandle::Close](../Topic/CHandle::Close.md)|`CHandle` のオブジェクトを閉じるために、このメソッドを呼び出します。|  
|[CHandle::Detach](../Topic/CHandle::Detach.md)|`CHandle` のオブジェクトのハンドルをデタッチするために、このメソッドを呼び出します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CHandle::operator HANDLE](../Topic/CHandle::operator%20HANDLE.md)|格納されているハンドルの値を返します。|  
|[CHandle::operator \=](../Topic/CHandle::operator%20=.md)|代入演算子。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CHandle::m\_h](../Topic/CHandle::m_h.md)|ハンドルを格納するメンバー変数。|  
  
## 解説  
 `CHandle` のオブジェクトは、ハンドルが必要なときに使用できる: 主な違いは `CHandle` のオブジェクトが自動的に削除されます。  
  
> [!NOTE]
>  一部の API 関数は、が空または無効なハンドルとして他、INVALID\_HANDLE\_VALUE を使用しますが、NULL を使用します。  `CHandle` の使用のみ実際のハンドルとして INVALID\_HANDLE\_VALUE を無効にし、処理します。  INVALID\_HANDLE\_VALUE を返すことができる API を呼び出す場合はこの値を持つように [CHandle::Attach](../Topic/CHandle::Attach.md) を呼び出すか、`CHandle` のコンストラクターに渡す前に確認するに null 値を渡します。  
  
## 必要条件  
 **ヘッダー:** atlbase.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)