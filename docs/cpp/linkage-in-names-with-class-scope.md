---
title: "クラス スコープを持つ名前にあるリンケージ | Microsoft Docs"
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
  - "クラス名 [C++], リンケージ"
  - "クラス スコープ [C++], リンケージ (名前の中)"
  - "クラス [C++], 名前"
  - "クラス [C++], スコープ"
  - "外部リンケージ, スコープ リンケージの規則"
  - "リンケージ [C++], スコープ リンケージの規則"
  - "名前 [C++], スコープ リンケージの規則"
  - "スコープ [C++], クラス名"
  - "スコープ [C++], リンケージの規則"
ms.assetid: 45275ff3-6e94-4967-82c8-ba540ef4da28
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# クラス スコープを持つ名前にあるリンケージ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス スコープの名前には、次のリンケージ規則が適用されます。  
  
-   静的クラス メンバーは外部リンケージを持ちます。  
  
-   クラスのメンバー関数は外部リンケージを持ちます。  
  
-   列挙子と `typedef` 名はリンケージを持ちません。  
  
 **Microsoft 固有の仕様 →**  
  
-   `friend` 関数として宣言された関数には、外部リンケージが必要です。  静的関数を `friend` として宣言すると、エラーが発生します。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [プログラムとリンケージ](../cpp/program-and-linkage-cpp.md)