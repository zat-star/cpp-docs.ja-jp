---
title: "値型とその動作 (C++/CLI) | Microsoft Docs"
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
  - "値型"
ms.assetid: 5cb872a6-1e0a-429d-853d-df4ab47e8f2a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 値型とその動作 (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

値型は、[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] ではさまざまな点で C\+\+ マネージ拡張から変更されています。  ここでは、CLR の列挙型および値のクラス型について説明し、ボックス化および CLR ヒープ上のボックス化されたインスタンスへのアクセスについて説明します。また、内部および固定ポインターについても説明します。  この分野では言語が広範に変更されています。  
  
## このセクションの内容  
 [CLR Enum Type](../dotnet/value-types-and-their-behaviors-cpp-cli.md)  
 列挙型 \(Enum\) の宣言および動作の変更点について説明します。  
  
 [値型の暗黙のボックス化](../dotnet/implicit-boxing-of-value-types.md)  
 値型の暗黙のボックス化の動機およびそれに伴う動作の変更点について説明します。  
  
 [追跡ハンドルからボックス化変換された値へ](../dotnet/a-tracking-handle-to-a-boxed-value.md)  
 値型の暗黙のボックス化が、ボックス化された値オブジェクトの追跡ハンドルにどのように変換されるかについて説明します。  
  
 [値型セマンティクス](../Topic/Value%20Type%20Semantics.md)  
 継承される仮想メソッド、クラスの既定コンストラクター、内部ポインター、固定ポインターなど、値型セマンティクスの変更点について説明します。  
  
## 参照  
 [C\+\+\/CLI 移行ガイド](../dotnet/cpp-cli-migration-primer.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)