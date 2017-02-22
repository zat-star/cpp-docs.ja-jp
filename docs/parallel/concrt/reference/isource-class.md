---
title: "ISource クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::ISource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISource クラス"
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# ISource クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`ISource` クラスは、すべてのソース ブロック用のインターフェイスです。  ソース ブロックは、メッセージを `ITarget` ブロックに伝達します。  
  
## 構文  
  
```  
template<  
   class _Type  
>  
class ISource;  
```  
  
#### パラメーター  
 `_Type`  
 ソース ブロックによって生成されるメッセージ内のペイロードのデータ型。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`source_type`|`_Type` の型のエイリアス。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[ISource::~ISource デストラクター](../Topic/ISource::~ISource%20Destructor.md)|`ISource` オブジェクトを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[ISource::accept メソッド](../Topic/ISource::accept%20Method.md)|派生クラスでオーバーライドされると、この `ISource` ブロックによって提供されたメッセージを受け付け、所有権を呼び出し元に移譲します。|  
|[ISource::acquire\_ref メソッド](../Topic/ISource::acquire_ref%20Method.md)|派生クラスでオーバーライドされると、この `ISource` ブロックの参照カウントを取得し、削除されるのを防ぎます。|  
|[ISource::consume メソッド](../Topic/ISource::consume%20Method.md)|派生クラスでオーバーライドされると、この `ISource` ブロックによって以前に提供され、ターゲットによって正常に予約されたメッセージを使用し、所有権を呼び出し元に移譲します。|  
|[ISource::link\_target メソッド](../Topic/ISource::link_target%20Method.md)|派生クラスでオーバーライドされると、ターゲット ブロックをこの `ISource` ブロックにリンクします。|  
|[ISource::release メソッド](../Topic/ISource::release%20Method.md)|派生クラスでオーバーライドされると、以前に正常に行われたメッセージの予約を解放します。|  
|[ISource::release\_ref メソッド](../Topic/ISource::release_ref%20Method.md)|派生クラスでオーバーライドされると、この `ISource` ブロックの参照カウントを解放します。|  
|[ISource::reserve メソッド](../Topic/ISource::reserve%20Method.md)|派生クラスでオーバーライドされると、この `ISource` ブロックによって以前に提供されたメッセージを予約します。|  
|[ISource::unlink\_target メソッド](../Topic/ISource::unlink_target%20Method.md)|派生クラスでオーバーライドされると、ターゲット ブロックのリンクをこの `ISource` ブロックから解除します \(以前にリンクされていた場合\)。|  
|[ISource::unlink\_targets メソッド](../Topic/ISource::unlink_targets%20Method.md)|派生クラスでオーバーライドされると、すべてのターゲット ブロックのリンクをこの `ISource` ブロックから解除します。|  
  
## 解説  
 詳細については、「[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。  
  
## 継承階層  
 `ISource`  
  
## 必要条件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ITarget クラス](../../../parallel/concrt/reference/itarget-class.md)