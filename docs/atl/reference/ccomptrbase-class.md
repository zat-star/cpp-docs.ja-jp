---
title: "CComPtrBase クラス | Microsoft Docs"
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
  - "ATL.CComPtrBase"
  - "ATL::CComPtrBase<T>"
  - "ATL.CComPtrBase<T>"
  - "ATL::CComPtrBase"
  - "CComPtrBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComPtrBase クラス"
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComPtrBase クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、COM ベースのメモリ ルーチンを使用するスマート ポインター クラスの基本クラスとなります。  
  
## 構文  
  
```  
  
      template <  
   class T   
> class CComPtrBase  
```  
  
#### パラメーター  
 `T`  
 スマート ポインターが参照するオブジェクト型。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComPtrBase::~CComPtrBase](../Topic/CComPtrBase::~CComPtrBase.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md)|`CComPtrBase` のコネクション ポイントとクライアント シンク間の接続を作成するには、このメソッドを呼び出します。|  
|[CComPtrBase::Attach](../Topic/CComPtrBase::Attach.md)|既存のポインターの所有権を持つようにこのメソッドを呼び出します。|  
|[CComPtrBase::CoCreateInstance](../Topic/CComPtrBase::CoCreateInstance.md)|指定したクラス ID に関連付けられたクラスのオブジェクトを作成するか、または ID をプログラムするには、このメソッドを呼び出します。|  
|[CComPtrBase::CopyTo](../Topic/CComPtrBase::CopyTo.md)|別のポインター変数に `CComPtrBase` のポインターをコピーする場合に、このメソッドを呼び出します。|  
|[CComPtrBase::Detach](../Topic/CComPtrBase::Detach.md)|ポインターの所有権を解放するためにこのメソッドを呼び出します。|  
|[CComPtrBase::IsEqualObject](../Topic/CComPtrBase::IsEqualObject.md)|同じへの **IUnknown** の指定した位置が `CComPtrBase` のオブジェクトに関連付けられたオブジェクトにはチェックするには、このメソッドを呼び出します。|  
|[CComPtrBase::QueryInterface](../Topic/CComPtrBase::QueryInterface.md)|特定のインターフェイスへのポインターを返すには、このメソッドを呼び出します。|  
|[CComPtrBase::Release](../Topic/CComPtrBase::Release.md)|インターフェイスを解放するためにこのメソッドを呼び出します。|  
|[CComPtrBase::SetSite](../Topic/CComPtrBase::SetSite.md)|親オブジェクトの **IUnknown** への `CComPtrBase` のオブジェクトのサイトを設定するには、このメソッドを呼び出します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CComPtrBase::operator T\*](../Topic/CComPtrBase::operator%20T*.md)|キャスト演算子。|  
|[CComPtrBase::operator \!](../Topic/CComPtrBase::operator%20!.md)|NOT 演算子です。|  
|[CComPtrBase::operator &](../Topic/CComPtrBase::operator%20&.md)|& 演算子。|  
|[CComPtrBase::operator \*](../Topic/CComPtrBase::operator%20*.md)|\*演算子。|  
|[CComPtrBase::operator \<](../Topic/CComPtrBase::operator%20%3C.md)|演算子より小さい。|  
|[CComPtrBase::operator \=\=](../Topic/CComPtrBase::operator%20==.md)|等値演算子。|  
|[CComPtrBase::operator \-\>](../Topic/CComPtrBase::operator%20-%3E.md)|ポインターメンバー演算子。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CComPtrBase::p](../Topic/CComPtrBase::p.md)|ポインターのデータ メンバー変数。|  
  
## 解説  
 このクラスには、COM メモリ管理ルーチンを使用すると [CComQIPtr](../../atl/reference/ccomqiptr-class.md)[CComPtr](../../atl/reference/ccomptr-class.md)などのスマート ポインターの基盤を提供します。  派生クラスは、独自のコンストラクターと演算子を追加しますが、`CComPtrBase`によって提供されるメソッドに依存します。  
  
## 必要条件  
 **ヘッダー :** atlcomcli.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)