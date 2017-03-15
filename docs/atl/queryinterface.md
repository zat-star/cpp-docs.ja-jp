---
title: "QueryInterface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "インターフェイス, 可用性"
  - "インターフェイス, ポインター"
  - "QueryInterface メソッド"
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# QueryInterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オブジェクトが機能を表現できる機構が、静的に提供する \(インスタンス化される前に\) ですが、基本的な COM の機構は [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)という **IUnknown** のメソッドを使用することです。  
  
 すべてのインターフェイスは **IUnknown**から派生しているため、すべてのインターフェイスに `QueryInterface`の実装があります。  実装に関係なく、このメソッドは呼び出し元は、ポインターを取得するインターフェイスの IID を使用してオブジェクトを照会します。  また `AddRef`の呼び出し中にインターフェイスをサポートするオブジェクト、`QueryInterface` がインターフェイスへのポインターを取得します。  それ以外の場合は **E\_NOINTERFACE** のエラー コードを返します。  
  
 [参照カウント](../atl/reference-counting.md) の規則には常に従う必要があります。  ゼロに参照カウントをデクリメントするためのインターフェイス ポインターの **\[リリース\]** を呼び出すと、このポインターを使用しないでください。  ときどきオブジェクト \(つまり、参照カウントをインクリメントしませんの 1 つがインターフェイスへのポインターを取得する\) への弱い参照を取得する必要がある `QueryInterface` を **\[リリース\]**後に呼び出さないことで行います。は適切ではありません。  このような方法で取得されたポインターは無効なため、使用しないでください。  [\_ATL\_DEBUG\_INTERFACES](../Topic/_ATL_DEBUG_INTERFACES.md) が定義されているため、このマクロを定義すると、参照カウント バグを検出する便利な方法です。この場合も簡単に明確になります。  
  
## 参照  
 [COM の概要](../atl/introduction-to-com.md)   
 [QueryInterface: Navigating in an Object](http://msdn.microsoft.com/library/windows/desktop/ms687230)