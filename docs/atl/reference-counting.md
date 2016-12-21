---
title: "参照カウント | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRef メソッド [C++]"
  - "AddRef メソッド [C++], 参照カウント"
  - "参照カウント"
  - "参照カウント"
  - "references, カウント"
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 参照カウント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オブジェクトは、使用されなくなったことを考えると COM 自体は自動的にメモリからオブジェクトを削除することはありません。  代わりに、オブジェクト プログラマは、使われていないオブジェクトを削除する必要があります。  プログラマは、オブジェクトが参照カウントに基づいて削除できるかどうかを判定します。  
  
 COM オブジェクトはインターフェイスの参照カウントを管理するために **IUnknown** のメソッド、[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) と [\[リリース\]](http://msdn.microsoft.com/library/windows/desktop/ms682317)を使用します。  これらのメソッドを呼び出すための一般規則は次のとおりです:  
  
-   クライアントがインターフェイス ポインターを受け取るたびに、`AddRef` は、インターフェイス頼まれなければ必要があります。  
  
-   クライアントがインターフェイス ポインターを使用して終了するたびに、**\[リリース\]**を呼び出す必要があります。  
  
 簡単な実装では、`AddRef` の各呼び出しのインクリメントとデクリメントを **\[リリース\]** は、各オブジェクト内のカウンター変数にを呼び出します。  ゼロへの計算が戻ると、インターフェイス、ユーザーがなく、メモリから自身を削除 free があります。  
  
 参照カウントは、各オブジェクトへの参照 \(個々のインターフェイスにではなく\) 反映させるように実装できます。  この場合、参照カウントがゼロに達すると、各 `AddRef` と **\[リリース\]** は、オブジェクトの中央実装に、デリゲートと **\[リリース\]** の可用性オブジェクト全体を呼び出します。  
  
> [!NOTE]
>  `CComObject`と派生オブジェクトは **new** の演算子を使用して、参照カウントが 0 構成されます。  したがって、`AddRef` の呼び出しが正常に `CComObject`派生オブジェクトを作成した後で行う必要があります。  
  
## 参照  
 [COM の概要](../atl/introduction-to-com.md)   
 [Managing Object Lifetimes through Reference Counting](http://msdn.microsoft.com/library/windows/desktop/ms687260)