---
title: "イベント処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- attributes [C++], event handling
- intrinsic functions [C++], event handling
- event handling [C++], Visual C++
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1ae45cf1ea8b2540038bab12f28c244ed7b5de7a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="event-handling"></a>イベント処理
イベント処理は、主に COM クラスのサポートされている (通常 ATL クラスを使用して、COM オブジェクトを実装する C++ クラス、または[コクラス](../windows/coclass.md)属性)。  詳細については、次を参照してください。 [COM でのイベント処理](../cpp/event-handling-in-com.md)です。  
  
 イベント処理はネイティブ C++ クラス (COM オブジェクトを実装しない C++ クラス) でサポートされていますが、このサポートは推奨されておらず、将来のリリースでは削除されます。  詳細については、次を参照してください。[ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md)です。  
  
 イベント処理では、シングルスレッドおよびマルチスレッドの使用をサポートし、同時マルチスレッド アクセスからデータを保護できます。 また、サブクラスをイベント ソース クラスまたはイベント レシーバー クラスから派生させ、その派生クラスの拡張イベント ソースと拡張イベント受信をサポートします。  
  
 Visual C++ には、イベントとイベント ハンドラーを宣言するための属性とキーワードが含まれています。 イベント属性とキーワードは、CLR プログラムとネイティブ C++ プログラムで使用できます。  
  
|トピック|説明|  
|-----------|-----------------|  
|[event_source](../windows/event-source.md)|イベント ソースを作成します。|  
|[event_receiver](../windows/event-receiver.md)|イベント レシーバー (シンク) を作成します。|  
|[__event](../cpp/event.md)|イベントを宣言します。|  
|[__raise](../cpp/raise.md)|イベントの呼び出しサイトを強調します。|  
|[__hook](../cpp/hook.md)|ハンドラー メソッドをイベントに関連付けます。|  
|[__unhook](../cpp/unhook.md)|イベントからハンドラー メソッドの関連付けを解除します。|  
  
## <a name="see-also"></a>関連項目  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [イベント処理のサンプル](http://msdn.microsoft.com/en-us/cc0287d4-f92b-4da5-85fc-a0f186e16424)