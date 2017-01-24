---
title: "CComUnkArray クラス | Microsoft Docs"
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
  - "ATL.CComUnkArray"
  - "ATL.CComUnkArray<nMaxSize>"
  - "ATL::CComUnkArray<nMaxSize>"
  - "ATL::CComUnkArray"
  - "CComUnkArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComUnkArray クラス"
  - "コネクション ポイント [C++], 管理"
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComUnkArray クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは **IUnknown** のポインターを格納し、[IConnectionPointImpl](../Topic/IConnectionPointImpl%20Class.md) テンプレート クラスにパラメーターとして使用されるようにデザインされています。  
  
## 構文  
  
```  
template<  
   unsigned int nMaxSize  
>  
class CComUnkArray  
```  
  
#### パラメーター  
 *nMaxSize*  
 静的な配列で保持できる **IUnknown** ポインターの最大数。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComUnkArray::CComUnkArray](../Topic/CComUnkArray::CComUnkArray.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComUnkArray::Add](../Topic/CComUnkArray::Add.md)|配列に **IUnknown** のポインターを追加するには、このメソッドを呼び出します。|  
|[CComUnkArray::begin](../Topic/CComUnkArray::begin.md)|コレクションの **IUnknown** の最初のポインターへのポインターを返します。|  
|[CComUnkArray::end](../Topic/CComUnkArray::end.md)|コレクションの **IUnknown** の最後のポインターを含む 1 個へのポインターを返します。|  
|[CComUnkArray::GetCookie](../Topic/CComUnkArray::GetCookie.md)|クッキーを **IUnknown** の特定のポインターに関連付けられているを取得するときにこのメソッドを呼び出します。|  
|[CComUnkArray::GetUnknown](../Topic/CComUnkArray::GetUnknown.md)|**IUnknown** のポインターを特定のクッキーに関連付けられているを取得するときにこのメソッドを呼び出します。|  
|[CComUnkArray::Remove](../Topic/CComUnkArray::Remove.md)|配列から **IUnknown** のポインターを削除するには、このメソッドを呼び出します。|  
  
## 解説  
 **CComUnkArray** は、各 **IUnknown** のポインターの数をコネクション ポイント インターフェイス保持します。  **CComUnkArray** は [IConnectionPointImpl](../Topic/IConnectionPointImpl%20Class.md) テンプレートのクラスへのパラメーターとして使用できます。  **CComUnkArray\<1\>** は 1 個のコネクション ポイント用に最適化された **CComUnkArray** テンプレートから特化したクラスです。  
  
 イベントが発生すると\) すべてのコネクション ポイントを反復処理するために **CComUnkArray** のメソッド [開始します。](../Topic/CComUnkArray::begin.md) と [終了](../Topic/CComUnkArray::end.md) を使用できます \(たとえば。  
  
 コネクション ポイントのプロキシの作成の自動化の詳細については [オブジェクトへのコネクション ポイントの追加](../../atl/adding-connection-points-to-an-object.md) を参照してください。  
  
> [!NOTE]
>  **Note** は **Add Class** ウィザードでクラス [CComDynamicUnkArray](../Topic/CComDynamicUnkArray%20Class.md) コネクション ポイントを持つコントロールを作成するときに使用します。  接続ポイントの数を手動で指定するには *、n は* 必要な接続ポイントの数である場合に、**CComDynamicUnkArray** から `CComUnkArray<` *n* `>`への参照を変更します。  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [CComDynamicUnkArray クラス](../Topic/CComDynamicUnkArray%20Class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)