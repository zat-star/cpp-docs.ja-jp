---
title: "ctype クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ctype"
  - "std::ctype"
  - "std.ctype"
  - "CType"
  - "xlocale/std::ctype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ctype クラス"
ms.assetid: 3627154c-49d9-47b5-b28f-5bbedee38e3b
caps.latest.revision: 19
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ctype クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

文字の分類、大文字と小文字の変換、およびネイティブ文字セットとロケールで使用される文字セットとの変換に使用されるふぁセットを提供するクラス。  
  
## 構文  
  
```  
template <class CharType>  
   class ctype : public ctype_base;  
```  
  
#### パラメーター  
 `CharType`  
 文字をエンコードするためにプログラム内で使用される型。  
  
## 解説  
 すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。  格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。分類の条件は、基底クラス ctype\_base の入れ子になったビットマスク型で提供されます。  
  
 標準 C\+\+ ライブラリは、このテンプレート クラスの 2 つの明示的な特殊化を定義します。  
  
-   [ctype](#vclrf_locale_ctype_class)\<`char`\>。違いが別個に記述される明示的な特殊化です。  
  
-   **ctype**\<`wchar_t`\>。要素をワイド文字として扱います。  
  
 テンプレート クラス **ctype**\<**CharType**\> のその他の特殊化。  
  
-   式 \(`char`\)**ch** を使用して、**CharType** 型の値 ***ch*** を、`char` 型の値に変換します。  
  
-   式 **CharType** \(**byte**\) を使用して、`char` 型の値 ***byte*** を、**CharType** 型の値に変換します。  
  
 他の操作はすべて明示的な特殊化 **ctype**\<`char`\> の場合と同様に `char` 値に対して実行されます。  
  
### コンストラクター  
  
|||  
|-|-|  
|[ctype](../Topic/ctype::ctype.md)|文字のロケール ファセットとして機能する `ctype` クラスのオブジェクトのコンストラクター。|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/ctype::char_type.md)|ロケールによって使用される文字を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[do\_is](../Topic/ctype::do_is.md)|1 つの文字が特定の属性を持つかどうかをテストしたり、範囲内の各文字の属性を分類して配列に格納したりするために呼び出される仮想関数。|  
|[do\_narrow](../Topic/ctype::do_narrow.md)|ロケールで使用される `CharType` 型の文字を、ネイティブ文字セットの `char` 型の対応する文字に変換するために呼び出される仮想関数。|  
|[do\_scan\_is](../Topic/ctype::do_scan_is.md)|指定されたマスクに一致する範囲内の最初の文字を検索するために呼び出される仮想関数。|  
|[do\_scan\_not](../Topic/ctype::do_scan_not.md)|指定されたマスクに一致しない範囲内の最初の文字を検索するために呼び出される仮想関数。|  
|[do\_tolower](../Topic/ctype::do_tolower.md)|文字または文字の範囲を小文字に変換するために呼び出される仮想関数。|  
|[do\_toupper](../Topic/ctype::do_toupper.md)|文字または文字の範囲を大文字に変換するために呼び出される仮想関数。|  
|[do\_widen](../Topic/ctype::do_widen.md)|ネイティブ文字セットの `char` 型の文字を、ロケールで使用される `CharType` 型の対応する文字に変換するために呼び出される仮想関数。|  
|[is](../Topic/ctype::is.md)|1 つの文字が特定の属性を持つかどうかをテストするか、範囲内の各文字の属性を分類して配列に格納します。|  
|[narrow](../Topic/ctype::narrow.md)|ロケールで使用される `CharType` 型の文字を、ネイティブ文字セットの char 型の対応する文字に変換します。|  
|[scan\_is](../Topic/ctype::scan_is.md)|指定されたマスクに一致する範囲内の最初の文字を検索します。|  
|[scan\_not](../Topic/ctype::scan_not.md)|指定されたマスクに一致しない範囲内の最初の文字を検索します。|  
|[tolower](../Topic/ctype::tolower.md)|文字または文字の範囲を小文字に変換します。|  
|[toupper](../Topic/ctype::toupper.md)|文字または文字の範囲を大文字に変換します。|  
|[widen](../Topic/ctype::widen.md)|ネイティブ文字セットの `char` 型の文字を、ロケールで使用される `CharType` 型の対応する文字に変換します。|  
  
## 必要条件  
 **ヘッダー:** \<locale\>  
  
 **名前空間:** std  
  
## 参照  
 [\<locale\>](../standard-library/locale.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)