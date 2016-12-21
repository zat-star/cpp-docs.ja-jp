---
title: "ITarget クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::ITarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITarget クラス"
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
caps.latest.revision: 22
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ITarget クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`ITarget` クラスは、すべてのターゲット ブロックのインターフェイスです。  ターゲット ブロックは、`ISource` ブロックから提供されたメッセージを処理します。  
  
## 構文  
  
```  
template<  
   class _Type  
>  
class ITarget;  
```  
  
#### パラメーター  
 `_Type`  
 ターゲット ブロックが受け取るメッセージ内のペイロードのデータ型。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`filter_method`|提供されたメッセージを受け付けるかどうかの判定として `bool` 値を返す、ブロックによって使用されるメソッドのシグネチャ。|  
|`type`|`_Type` の型のエイリアス。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[ITarget::~ITarget デストラクター](../Topic/ITarget::~ITarget%20Destructor.md)|`ITarget` オブジェクトを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[ITarget::propagate メソッド](../Topic/ITarget::propagate%20Method.md)|派生クラスでオーバーライドされると、ソース ブロックからこのターゲット ブロックへと非同期的にメッセージを渡します。|  
|[ITarget::send メソッド](../Topic/ITarget::send%20Method.md)|派生クラスでオーバーライドされると、このターゲット ブロックへと同期的にメッセージを渡します。|  
|[ITarget::supports\_anonymous\_source メソッド](../Topic/ITarget::supports_anonymous_source%20Method.md)|派生クラスでオーバーライドされた場合は、メッセージ ブロックがリンクされていないソースによって提供されたメッセージを受け付けるかどうかは、false 調整します。  オーバーライドされたメソッドが `true`を返した場合、ターゲットは遅延メッセージの消費が後にソースが sourse リンク レジストリで識別される必要があるため、提供されたメッセージを実行できません。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[ITarget::link\_source メソッド](../Topic/ITarget::link_source%20Method.md)|派生クラスでオーバーライドされると、指定されたソース ブロックをこの `ITarget` ブロックにリンクします。|  
|[ITarget::unlink\_source メソッド](../Topic/ITarget::unlink_source%20Method.md)|派生クラスでオーバーライドされると、指定されたソース ブロックとこの `ITarget` ブロックとのリンクを解除します。|  
|[ITarget::unlink\_sources メソッド](../Topic/ITarget::unlink_sources%20Method.md)|派生クラスでオーバーライドされると、すべてのソース ブロックとこの `ITarget` ブロックとのリンクを解除します。|  
  
## 解説  
 詳細については、「[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。  
  
## 継承階層  
 `ITarget`  
  
## 必要条件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ISource クラス](../../../parallel/concrt/reference/isource-class.md)