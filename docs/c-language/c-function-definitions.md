---
title: "C 関数定義 | Microsoft Docs"
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
  - "宣言子, 関数"
  - "宣言 (関数を), 関数宣言の概要"
  - "宣言 (関数を), 宣言子"
  - "宣言 (関数を), 変数"
  - "関数本体"
  - "関数宣言"
  - "関数定義"
  - "関数パラメーター, 関数定義"
  - "関数 [C], パラメーター"
ms.assetid: ebab23c8-6eb8-46f3-b21d-570cd8457a80
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C 関数定義
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関数定義は、関数の名前、受け取ることを想定するパラメーターの種類と数、および戻り値の型を指定します。  関数定義には、ローカル変数の宣言を持つ関数本体と、関数の処理を決定するステートメントも含まれます。  
  
## 構文  
 *translation\-unit*:  
 *external\-declaration*  
  
 *translation\-unit external\-declaration*  
  
 *external\-declaration*: \/\* 外部 \(ファイル\) スコープでのみ使用できる \*\/  
 *function\-definition*  
  
 `declaration`  
  
 *function\-definition*: \/\* この宣言子は関数宣言子 \*\/  
 *declaration\-specifiers*  opt *attribute\-seq* opt *declarator declaration\-list* opt *compound\-statement*  
  
 \/\* *attribute\-seq* は Microsoft 固有の仕様 \*\/  
  
 プロトタイプ パラメーターは次のとおりです。  
  
 *declaration\-specifiers*:  
 *storage\-class\-specifier declaration\-specifiers*  opt  
  
 *type\-specifier declaration\-specifiers*  opt  
  
 *type\-qualifier declaration\-specifiers*  opt  
  
 *declaration\-list*:  
 *declaration*  
  
 *declaration\-list declaration*  
  
 `declarator`:  
 *pointer*  opt *direct\-declarator*  
  
 *direct\-declarator*: \/\* 関数宣言子 \*\/  
 *direct\-declarator*  **\(**  *parameter\-type\-list*  **\)** \/\* 新しい形式の宣言子 \*\/  
  
 *direct\-declarator*  **\(**  *identifier\-list*  opt **\)** \/\* 古い形式の宣言子 \*\/  
  
 定義のパラメーター リストは、この構文を使用します。  
  
 *parameter\-type\-list*: \/\* パラメーター リスト \*\/  
 *parameter\-list*  
  
 *parameter\-list* **, ...**  
  
 *parameter\-list*:  
 *parameter\-declaration*  
  
 *parameter\-list* **,**  *parameter\-declaration*  
  
 *parameter\-declaration*:  
 *declaration\-specifiers declarator*  
  
 *declaration\-specifiers abstract declarator*  opt  
  
 旧式の関数定義のパラメーター リストは、この構文を使用します。  
  
 *identifier\-list*: \/\* 古い形式の関数定義と宣言で使用します \*\/  
 *identifier*  
  
 *identifier\-list* **,**  *identifier*  
  
 関数本体の構文は次のとおりです。  
  
 *compound\-statement*: \/\* 関数本体 \*\/  
 **{**  `declaration`\-*list* opt *statement\-list* opt **}**  
  
 関数宣言を変更できるストレージ クラスの指定子は `extern` と **static** だけです。  `extern` 指定子は、関数が他のファイルから参照できること、つまり、関数名はリンカーにエクスポートされることを指定します。  **static** 指定子は、関数が他のファイルから参照できないこと、つまり、名前がリンカーによってエクスポートされないことを指定します。  ストレージ クラスが関数定義に表示されない場合、`extern` と見なされます。  いずれの場合も、関数は定義位置からファイルの末尾まで常に参照可能です。  
  
 省略可能な *declaration\-specifiers* と必須の `declarator` は、関数の戻り値の型と名前を指定します。  `declarator` は、関数の名前を指定する識別子と関数名の後に続くかっこの組み合わせです。  必須ではない要素の *attribute\-seq* は、「[関数の属性](../Topic/Function%20Attributes.md)」で定義する Microsoft 固有の機能です。  
  
 *direct\-declarator* \(`declarator` 構文内\) は、定義されている関数の名前とそのパラメーターの ID を指定します。  \<direct\-declarator\> に \<parameter\-type\-list\> が含まれる場合、そのリストですべてのパラメーターの型を指定します。  このような宣言は、それ以降の関数の呼び出しに対する関数プロトタイプとしても機能します。  
  
 関数定義の *declaration\-list* の `declaration` は、**register** 以外の *storage\-class\-specifier* を含めることはできません。  *declaration\-specifiers* 構文の *type\-specifier* は、**register** ストレージ クラスが `int` 型の値に対して指定されている場合にのみ省略できます。  
  
 *compound\-statement* は、ローカル変数宣言、外部で宣言された項目への参照、およびステートメントを含む関数本体です。  
  
 「[関数の属性](../Topic/Function%20Attributes.md)」、「[ストレージ クラス](../Topic/Storage%20Class.md)」、「[戻り値の型](../Topic/Return%20Type.md)」、「[パラメーター](../c-language/parameters.md)」、および「[関数本体](../Topic/Function%20Body.md)」の各セクションでは、関数定義のコンポーネントについて詳しく説明します。  
  
## 参照  
 [関数](../Topic/Functions%20\(C\).md)