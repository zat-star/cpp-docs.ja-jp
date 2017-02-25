---
title: "message クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::message"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message クラス"
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# message クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

メッセージング ブロック間で渡されるデータ ペイロードが格納される、基本的なメッセージ エンベロープ。  
  
## 構文  
  
```  
template<  
   class _Type  
>  
class message : public ::Concurrency::details::_Runtime_object;  
```  
  
#### パラメーター  
 `_Type`  
 メッセージ内のペイロードのデータ型。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`type`|`_Type` の型のエイリアス。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[message::message コンストラクター](../Topic/message::message%20Constructor.md)|オーバーロードされます。  `message` オブジェクトを構築します。|  
|[message::~message デストラクター](../Topic/message::~message%20Destructor.md)|`message` オブジェクトを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[message::add\_ref メソッド](../Topic/message::add_ref%20Method.md)|`message` オブジェクトの参照カウントを加算します。  メッセージの有効期間を判別するために参照カウントが必要なメッセージ ブロックで使用されます。|  
|[message::msg\_id メソッド](../Topic/message::msg_id%20Method.md)|`message` オブジェクトの ID を返します。|  
|[message::remove\_ref メソッド](../Topic/message::remove_ref%20Method.md)|`message` オブジェクトの参照カウントを減算します。  メッセージの有効期間を判別するために参照カウントが必要なメッセージ ブロックで使用されます。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[message::payload データ メンバー](../Topic/message::payload%20Data%20Member.md)|`message` オブジェクトのペイロード。|  
  
## 解説  
 詳細については、「[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。  
  
## 継承階層  
 `message`  
  
## 必要条件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)