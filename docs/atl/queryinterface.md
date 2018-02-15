---
title: "QueryInterface |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce14ebef3649cea78e8cf4315a62392cfa142152
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="queryinterface"></a>QueryInterface
基本的な COM 機構は使用するメカニズムでオブジェクトが静的に (前にインスタンス化される) を提供する機能を表すことができますが、 **IUnknown**呼び出されるメソッド[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 派生したすべてのインターフェイスは**IUnknown**ですべてのインターフェイスの実装を持つため、`QueryInterface`です。 実装に関係なくは、このメソッドは、呼び出し元がポインターを希望するインターフェイスの IID を使用してオブジェクトを照会します。 オブジェクトは、そのインターフェイスをサポートしている場合`QueryInterface`もの呼び出し中に、インターフェイスへのポインターを取得`AddRef`です。 返しますそれ以外の場合、 **E_NOINTERFACE**エラー コード。  
  
 従う必要があります注[参照カウント](../atl/reference-counting.md)常時ルール。 呼び出す場合**リリース**をゼロに参照カウントをデクリメントするためのインターフェイス ポインターで使用しないでそのポインターもう一度です。 場合によっては、オブジェクトへの弱い参照を取得する必要があります (つまり、する場合、参照カウントをインクリメントせずにそのインターフェイスのいずれかへのポインターを取得)、呼び出すことによってこれに余裕がないが、`QueryInterface`続く**リリース**です。 このような方法で取得したポインターは有効は使用できません。 これより容易に明らかになるとき[_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces)が定義されている場合は、検索する参照がカウントのバグの便利な方法は、このマクロを定義するようにします。  
  
## <a name="see-also"></a>参照  
 [COM の概要](../atl/introduction-to-com.md)   
 [QueryInterface: オブジェクト間の移動](http://msdn.microsoft.com/library/windows/desktop/ms687230)

