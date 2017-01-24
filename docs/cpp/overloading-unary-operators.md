---
title: "単項演算子のオーバーロード | Microsoft Docs"
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
  - "インクリメント演算子, オーバーロード"
  - "演算子 [C++], 単項"
  - "plus 演算子"
  - "ポインター逆参照演算子のオーバーロード"
  - "再定義可能な単項演算子"
  - "単項演算子"
  - "単項演算子, minus"
  - "単項演算子, plus"
ms.assetid: 7683ef08-42a4-4283-928f-d3dd4f3ab4c0
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 単項演算子のオーバーロード
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オーバーロードできる単項演算子は次のとおりです。  
  
1.  `!` \([論理 NOT](../cpp/logical-negation-operator-exclpt.md)\)  
  
2.  `&` \([アドレス取得](../cpp/address-of-operator-amp.md)\)  
  
3.  `~` \([1 の補数](../cpp/one-s-complement-operator-tilde.md)\)  
  
4.  `*` \([ポインター逆参照](../cpp/indirection-operator-star.md)\)  
  
5.  `+` \([単項プラス](../cpp/additive-operators-plus-and.md)\)  
  
6.  `-` \([単項マイナス符号](../cpp/additive-operators-plus-and.md)\)  
  
7.  `++` \([インクリメント](../Topic/Prefix%20Increment%20and%20Decrement%20Operators:%20++%20and%20--.md)\)  
  
8.  `--` \([デクリメント](../Topic/Prefix%20Increment%20and%20Decrement%20Operators:%20++%20and%20--.md)\)  
  
9. 変換演算子  
  
 後置インクリメントとデクリメント演算子 \(`++` と **\-\-**\) は「[インクリメントとデクリメント](../Topic/Increment%20and%20Decrement%20Operator%20Overloading%20\(C++\).md)」で個別に取り上げます。  
  
 変換演算子も個別のトピックで説明します \(「[変換](../cpp/user-defined-type-conversions-cpp.md)」を参照\)。  
  
 次の規則は他のすべての単項演算子に適用されます。  単項演算子関数を非静的メンバーとして宣言するには、次の形式で宣言する必要があります。  
  
 `ret-type operator` `op` `()`  
  
 `ret-type` は戻り値の型であり、`op` は前の表に示している演算子の 1 つです。  
  
 単項演算子関数をグローバル関数として宣言するには、次の形式で宣言する必要があります。  
  
 `ret-type operator` `op` \(`arg` \)  
  
 `ret-type` と `op` はメンバー演算子関数での説明と同様です。`arg` は操作対象のクラス型の引数です。  
  
> [!NOTE]
>  単項演算子の戻り値の型に制限はありません。  たとえば、論理 NOT \(`!`\) が整数値を返すのは正しい使い方ですが、強制ではありません。  
  
## 参照  
 [演算子のオーバーロード](../cpp/operator-overloading.md)