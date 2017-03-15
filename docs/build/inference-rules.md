---
title: "推論規則 | Microsoft Docs"
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
  - "推論規則 (NMAKE の)"
  - "NMAKE プログラム, 推論規則"
  - "規則, 推論"
ms.assetid: caff320f-fb07-4eea-80c3-a6a2133a8492
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 推論規則
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

推論規則では、ターゲットを更新したり、ターゲットの依存ファイルを推論したりするコマンドが用意されます。  推論規則の拡張子は、同じベース名を持つ 1 つのターゲットおよび依存ファイルと一致します。  推論規則には、ユーザー定義の規則と組み込みの規則があります。組み込みの規則は、再定義できます。  
  
 古い依存関係にコマンドがない場合、[.SUFFIXES](../build/dot-directives.md) に依存ファイルの拡張子が格納されていると、NMAKE は、拡張子がターゲットおよび現在のディレクトリまたは指定されたディレクトリにある既存のファイルと一致する規則を使用します。  複数の規則が既存のファイルと一致する場合は、**.SUFFIXES** リストでどの規則を使用するかが判断されます。リストの優先順位は、左から右の順です。  依存ファイルが存在せず、別の記述ブロックでターゲットとして指定されていない場合、推論規則では、同じベース名の別のファイルから足りない依存ファイルを作成できます。  記述ブロックのターゲットに依存ファイルやコマンドがない場合、推論規則ではターゲットを更新できます。  推論規則では、記述ブロックが存在しない場合でも、コマンド ライン ターゲットをビルドできます。  NMAKE では、明示的な依存ファイルが指定されている場合でも、推論による依存ファイルの規則を呼び出すことがあります。  
  
## さらに詳しくは次のトピックをクリックしてください  
 [規則の定義](../build/defining-a-rule.md)  
  
 [バッチモード規則](../Topic/Batch-Mode%20Rules.md)  
  
 [定義済み規則](../build/predefined-rules.md)  
  
 [推論による依存ファイルと推論規則](../build/inferred-dependents-and-rules.md)  
  
 [推論規則の優先順位](../build/precedence-in-inference-rules.md)  
  
## 参照  
 [NMAKE リファレンス](../build/nmake-reference.md)