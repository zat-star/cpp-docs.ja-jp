---
title: "ファイル スコープを持つ名前にあるリンケージ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "宣言 [C++], 外部"
  - "外部リンケージ, スコープ リンケージの規則"
  - "ファイル スコープ [C++]"
  - "リンケージ [C++], スコープ リンケージの規則"
  - "名前 [C++], スコープ リンケージの規則"
  - "スコープ [C++], リンケージの規則"
  - "static 修飾子, ファイル スコープ"
  - "静的な名前とファイル スコープ"
  - "静的変数, 外部宣言"
ms.assetid: 38d3fa5e-1861-466e-a590-84b86f7b184e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ファイル スコープを持つ名前にあるリンケージ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のリンケージ規則は、ファイル スコープを持つ名前 \(`typedef` と列挙子の名前以外\) に適用されます。  
  
-   名前が **static** として明示的に宣言されている場合、その名前は内部リンケージを持ち、プログラム要素を独自の翻訳単位内で識別します。  
  
-   列挙子名と `typedef` 名はリンケージを持ちません。  
  
-   ファイル スコープを持つ他のすべての名前は外部リンケージを持ちます。  
  
 **Microsoft 固有の仕様 →**  
  
-   ファイル スコープを持つ関数名が **inline** として明示的に宣言されると、その関数がインスタンス化される場合やそのアドレスが参照される場合、関数名は外部リンケージを持ちます。  したがって、ファイル スコープを持つ関数は内部または外部リンケージを持つことができます。  
  
 **END Microsoft 固有の仕様**  
  
 次の場合、クラスは内部リンケージを持ちます。  
  
-   C\+\+ の機能を使用していません \(たとえば、メンバー アクセス制御、メンバー関数、コンストラクター、デストラクターなど\)。  
  
-   外部リンケージを持つ別の名前の宣言で使用されていません。  この制約は、外部リンケージを持つ関数に渡されるクラス型のオブジェクトにより、クラスが外部リンケージを持つことを意味します。  
  
## 参照  
 [プログラムとリンケージ](../cpp/program-and-linkage-cpp.md)