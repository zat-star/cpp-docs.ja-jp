---
title: "C ストレージ クラス | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "有効期間, 変数"
  - "指定子, ストレージ クラス"
  - "静的変数, 有効期間"
  - "ストレージ クラス指定子, C のストレージ クラス"
  - "ストレージ クラス"
  - "ストレージ継続期間"
ms.assetid: 893fb929-f7a9-43dc-a0b3-29cb1ef845c1
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C ストレージ クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

変数の "ストレージ クラス" は、項目が "グローバルな" 有効期間を持つか、"ローカルな" 有効期間を持つかを決定します。  C では、これら 2 つの有効期間を "static" および "automatic" と呼びます。 グローバル有効期間を持つ項目は、プログラムの実行全体に値があります。  すべての関数にはグローバル有効期間があります。  
  
 ローカル有効期間を持つ自動変数、または変数は、自分が定義されているブロックに実行制御が渡されるたびに新しいストレージが割り当てられます。  実行から返るとき、変数には有効な値が含まれていません。  
  
 C には、次のストレージ クラス指定子が用意されています。  
  
## 構文  
 *storage\-class\-specifier*:  
 **auto**  
  
 **register**  
  
 **static**  
  
 **extern**  
  
 **typedef**  
  
 **\_\_declspec** \( *extended\-decl\-modifier\-seq* \) \/\* Microsoft 固有の仕様 \*\/  
  
 `__declspec` を除いて、宣言の *declaration\-specifier* では 1 個の *storage\-class\-specifier* のみ使用できます。  ストレージ クラスの指定が行われない場合、ブロック内の宣言により自動オブジェクトが作成されます。  
  
 **auto** または **register** 指定子で宣言された項目にはローカルの有効期間があります。  **static** または `extern` 指定子で宣言された項目にはグローバルの有効期間があります。  
  
 `typedef` および `__declspec` は他の 4 つの *storage\-class\-specifier* 必須要素とは意味が異なるため、個別に説明しています。  `typedef` の特定の情報については、「[Typedef の宣言](../c-language/typedef-declarations.md)」を参照してください。  `__declspec` の特定の情報については、「[拡張ストレージ クラス属性](../c-language/c-extended-storage-class-attributes.md)」を参照してください。  
  
 ソース ファイル内の変数と関数宣言の配置は、ストレージ クラスと可視性にも影響します。  すべての関数定義の外部にある宣言は、"外部レベル" での記述と呼ばれます。 関数定義内での宣言は、"内部レベル" で記述されます。  
  
 各ストレージ クラス指定子の厳密な意味は 2 つの要因に左右されます。  
  
-   宣言が現れるのが、外部レベルか内部レベルか  
  
-   宣言された項目が、変数または関数であるかどうか  
  
 「[外部レベル宣言のストレージ クラス指定子](../c-language/storage-class-specifiers-for-external-level-declarations.md)」および「[内部レベル宣言のストレージ クラス指定子](../c-language/storage-class-specifiers-for-internal-level-declarations.md)」では、各種宣言の *storage\-class\-specifier* 必須要素について記載し、変数から *storage\-class\-specifier* が省略されている場合の既定の動作について説明しています。  「[関数宣言を伴うストレージ クラス指定子](../Topic/Storage-Class%20Specifiers%20with%20Function%20Declarations.md)」では、関数と共に使用されるストレージ クラス指定子について説明します。  
  
## 参照  
 [型の宣言](../c-language/declarations-and-types.md)