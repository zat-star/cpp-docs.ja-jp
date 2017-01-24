---
title: "イベント処理 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "属性 [C++], イベント処理"
  - "イベント処理, Visual C++"
  - "組み込み関数, イベント処理"
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# イベント処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イベント処理は主に COM クラス \(一般的に ATL クラスまたは [coclass](../windows/coclass.md) の属性を使用して COM オブジェクトを実装する C\+\+ クラス\) でサポートされています。  詳細については、「[COM でのイベント処理](../cpp/event-handling-in-com.md)」を参照してください。  
  
 イベント処理はネイティブ C\+\+ クラス \(COM オブジェクトを実装しない C\+\+ クラス\) でサポートされていますが、このサポートは推奨されておらず、将来のリリースでは削除されます。  詳細については、「[ネイティブ C\+\+ でのイベント処理](../Topic/Event%20Handling%20in%20Native%20C++.md)」を参照してください。  
  
 イベント処理では、シングルスレッドおよびマルチスレッドの使用をサポートし、同時マルチスレッド アクセスからデータを保護できます。  また、サブクラスをイベント ソース クラスまたはイベント レシーバー クラスから派生させ、その派生クラスの拡張イベント ソースと拡張イベント受信をサポートします。  
  
 Visual C\+\+ には、イベントとイベント ハンドラーを宣言するための属性とキーワードが含まれています。  イベント属性とキーワードは、CLR プログラムとネイティブ C\+\+ プログラムで使用できます。  
  
|トピック|説明|  
|----------|--------|  
|[event\_source](../windows/event-source.md)|イベント ソースを作成します。|  
|[event\_receiver](../windows/event-receiver.md)|イベント レシーバー \(シンク\) を作成します。|  
|[\_\_event](../cpp/event.md)|イベントを宣言します。|  
|[\_\_raise](../cpp/raise.md)|イベントの呼び出しサイトを強調します。|  
|[\_\_hook](../cpp/hook.md)|ハンドラー メソッドをイベントに関連付けます。|  
|[\_\_unhook](../cpp/unhook.md)|イベントからハンドラー メソッドの関連付けを解除します。|  
  
## 参照  
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [Event Handling Samples](http://msdn.microsoft.com/ja-jp/cc0287d4-f92b-4da5-85fc-a0f186e16424)