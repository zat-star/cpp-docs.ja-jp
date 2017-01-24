---
title: "クラスまたはインターフェイス内でのメンバー宣言 (C++/CLI) | Microsoft Docs"
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
  - "クラス メンバー, 宣言の構文"
  - "メンバー, 宣言の構文"
ms.assetid: 95d312a4-198b-46f0-b8f5-15253807c55e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# クラスまたはインターフェイス内でのメンバー宣言 (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロパティと演算子の宣言は、[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では C\+\+ マネージ拡張から大幅に変更され、マネージ拡張デザインでは公開されていた基になる実装の詳細が隠蔽されています。  また、イベントの宣言も変更されています。  
  
 マネージ拡張ではサポートされない変更としては、静的コンストラクターをアウトオブラインで定義できること \(マネージ拡張ではインラインで定義する必要がありました\)、およびデリゲート コンストラクターの概念が導入されたことがあります。  
  
## このセクションの内容  
 [プロパティの宣言](../dotnet/property-declaration.md)  
 プロパティ宣言の変更について説明します。  
  
 [プロパティ インデックスの宣言](../dotnet/property-index-declaration.md)  
 インデックス付きプロパティの宣言の変更について説明します。  
  
 [デリゲートとイベント](../dotnet/delegates-and-events.md)  
 デリゲートおよびイベントを宣言する構文の変更について説明します。  
  
 [仮想関数のシール](../dotnet/sealing-a-virtual-function.md)  
 関数をシールする構文の変更について説明します。  
  
 [オーバーロードされた演算子](../dotnet/overloaded-operators.md)  
 演算子のオーバーロードに対する変更について説明します。  
  
 [変換演算子に対する変更点](../dotnet/changes-to-conversion-operators.md)  
 変換演算子の変更について説明します。  
  
 [インターフェイス メンバーの明示的なオーバーライド](../dotnet/explicit-override-of-an-interface-member.md)  
 インターフェイス メンバーを明示的にオーバーライドするメソッドの変更について説明します。  
  
 [プライベート仮想関数](../Topic/Private%20Virtual%20Functions.md)  
 プライベート仮想関数が派生クラスで処理される方法の変更について説明します。  
  
 [静的整数型定数リンケージの非リテラル化](../dotnet/static-const-int-linkage-is-no-longer-literal.md)  
 `static const` の整数メンバーがリンクされる方法、および新しい `literal` キーワードを使用して定数を明示的に宣言する方法の変更について説明します。  
  
## 参照  
 [C\+\+\/CLI 移行ガイド](../dotnet/cpp-cli-migration-primer.md)