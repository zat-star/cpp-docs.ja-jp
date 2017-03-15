---
title: "マーシャリング | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM インターフェイス, マーシャリング"
  - "マーシャリング"
  - "マーシャリング, COM 相互運用機能"
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# マーシャリング
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マーシャリングの COM 技術が別のプロセスで使用される 1 種類のプロセスのオブジェクトによって公開されるインターフェイスを使用できます。  マーシャリングでは、COM はコード \(またはインターフェイスの implementor が提供するプロセス間で、\(または、他のコンピューターで実行されるプロセスへのリンクで\) 実行され、それらのパラメーターをもう一方のアンロードを解除する形式にメソッドのパラメーターによっては、コードを使用\) 両方が用意されています。  同様に、COM に呼び出しから制御が返されるときにこれらの同じ手順を実行する必要があります。  
  
> [!NOTE]
>  マーシャリングは、オブジェクトによって提供されるインターフェイスがオブジェクトと同じプロセスで使用する場合、通常は必要ではありません。  ただし、マーシャリングはスレッド間で必要があります。  
  
## 参照  
 [COM の概要](../atl/introduction-to-com.md)   
 [Marshaling Details](http://msdn.microsoft.com/library/windows/desktop/ms692621)