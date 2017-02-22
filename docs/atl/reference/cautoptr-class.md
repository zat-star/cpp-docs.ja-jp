---
title: "CAutoPtr クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAutoPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoPtr クラス"
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CAutoPtr クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、スマート ポインター オブジェクトを表します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<   
typename T  
>  
class CAutoPtr  
```  
  
#### パラメーター  
 `T`  
 ポインター型。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAutoPtr::CAutoPtr](../Topic/CAutoPtr::CAutoPtr.md)|コンストラクターです。|  
|[CAutoPtr::~CAutoPtr](../Topic/CAutoPtr::~CAutoPtr.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAutoPtr::Attach](../Topic/CAutoPtr::Attach.md)|既存のポインターの所有権を持つようにこのメソッドを呼び出します。|  
|[CAutoPtr::Detach](../Topic/CAutoPtr::Detach.md)|ポインターの所有権を解放するためにこのメソッドを呼び出します。|  
|[CAutoPtr::Free](../Topic/CAutoPtr::Free.md)|指すにオブジェクトを `CAutoPtr`削除するには、このメソッドを呼び出します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CAutoPtr::operator T\*](../Topic/CAutoPtr::operator%20T*.md)|キャスト演算子。|  
|[CAutoPtr::operator \=](../Topic/CAutoPtr::operator%20=.md)|代入演算子です。|  
|[CAutoPtr::operator \-\>](../Topic/CAutoPtr::operator%20-%3E.md)|ポインターメンバー演算子。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAutoPtr::m\_p](../Topic/CAutoPtr::m_p.md)|ポインターのデータ メンバー変数。|  
  
## 解説  
 このクラスは自動的にリソースを解放することによって、範囲からメモリ リークする場合に対して保護するスマート ポインターを作成および管理するためのメソッドを提供します。  
  
 さらに、`CAutoPtr` のコピー コンストラクターと代入演算子は、コピー先のポインターにソースのポインターをコピーし、NULL にソースのポインターを置くポインターの所有権を譲渡されます。  したがって、同じポインターを格納 `CAutoPtr` の 2 種類のオブジェクトを個別に設定することはできなくなります。これにより、同じポインターを回削除する可能性が減少します。  
  
 `CAutoPtr` は、ポインターのコレクションを簡単に作成できます。  コレクション クラスを取得し、デストラクターをオーバーライドする代わりに、`CAutoPtr` のオブジェクトのコレクションを行いやすくなります。  コレクションが削除されるとき、`CAutoPtr` のオブジェクトがスコープ外に出て、自動的に自分自身を削除します。  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md) とバリアントは `CAutoPtr`と同じように動作します。ただし、C\+\+ **new** と **delete** の演算子の代わりに異なるヒープ関数を使用してメモリの割り当てと解放します。  [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) は `CAutoPtr`のメモリの割り当てと解放するに **vector new\[\]** と **vector delete\[\]** を使用することにある唯一の違いに似ています。  
  
 スマート ポインターの配列またはリストが要求されると [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) と [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) を参照してください。  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 使用例  
 [!CODE [NVC_ATL_Utilities#74](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#74)]  
  
## 参照  
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [CAutoVectorPtr クラス](../../atl/reference/cautovectorptr-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)