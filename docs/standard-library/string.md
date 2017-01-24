---
title: "&lt;string&gt; | Microsoft Docs"
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
  - "std::<string>"
  - "string/std::<string>"
  - "std.<string>"
  - "<string>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "string ヘッダー"
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
caps.latest.revision: 23
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;string&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンテナーのテンプレート クラス `basic_string` とさまざまなサポート用テンプレートを定義します。  
  
 `basic_string` の詳細については、「[basic\_string クラス](../standard-library/basic-string-class.md)」を参照してください。  
  
## 構文  
  
```  
#include <string>  
```  
  
## 解説  
 C\+\+ 言語および標準 C\+\+ ライブラリでは、2 種類の文字列がサポートされます。  
  
-   よく C 文字列と呼ばれる、null で終わる文字の配列。  
  
-   `char` に類するすべてのテンプレート引数を処理する、`basic_string` 型のテンプレート クラス オブジェクト。  
  
### Typedef  
  
|||  
|-|-|  
|[string](../Topic/string%20\(C++%20STL%20%3Cstring%3E\).md)|`char` 型の要素を `string` として特殊化したテンプレート クラス `basic_string` を記述する型。|  
|[wstring](../Topic/wstring.md)|`wchar_t` 型の要素を `wstring` として特殊化したテンプレート クラス `basic_string` を記述する型。|  
|[u16string](../Topic/u16string.md)|`char16_t` 型の要素に基づいて特殊化したテンプレート クラス `basic_string` を記述する型。|  
|[u32string](../Topic/u32string.md)|`char32_t` 型の要素に基づいて特殊化したテンプレート クラス `basic_string` を記述する型。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\+](../Topic/operator+%20\(%3Cstring%3E\).md)|2 つの文字列オブジェクトを連結します。|  
|[operator\!\=](../Topic/operator!=%20\(%3Cstring%3E\).md)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトと等しくないかどうかを調べます。|  
|[operator\=\=](../Topic/operator==%20\(%3Cstring%3E\).md)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトと等しいかどうかを調べます。|  
|[\< 演算子](../Topic/operator%3C%20\(%3Cstring%3E\).md)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトより小さいかどうかを調べます。|  
|[\<\= 演算子](../Topic/operator%3C=%20\(in%20%3Cstring%3E\).md)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクト以下かどうかを調べます。|  
|[演算子 \<\<](../Topic/operator%3C%3C%20\(%3Cstring%3E\).md)|出力ストリームに文字列を挿入するテンプレート関数。|  
|[\> 演算子](../Topic/operator%3E%20\(%3Cstring%3E\).md)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトより大きいかどうかを調べます。|  
|[\>\= 演算子](../Topic/operator%3E=%20\(%3Cstring%3E\).md)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクト以上かどうかを調べます。|  
|[演算子 \>\>](../Topic/operator%3E%3E%20\(%3Cstring%3E\).md)|入力ストリームから文字列を抽出するテンプレート関数。|  
  
### 特殊テンプレート関数  
  
|||  
|-|-|  
|[swap](../Topic/swap%20\(C++%20STL%20%3Cstring%3E\).md)|2 つの文字列の、文字の配列を交換します。|  
|[stod](../Topic/stod.md)|文字シーケンスを `double.` に変換します。|  
|[stof](../Topic/stof.md)|文字シーケンスを `float` に変換します。|  
|[stoi](../Topic/stoi.md)|文字シーケンスを integer に変換します。|  
|[stold](../Topic/stold.md)|文字シーケンスを `long double` に変換します。|  
|[stoll](../Topic/stoll.md)|文字シーケンスを `long long` に変換します。|  
|[stoul](../Topic/stoul.md)|文字シーケンスを `unsigned long` に変換します。|  
|[stoull](../Topic/stoull.md)|文字シーケンスを `unsigned long long` に変換します。|  
|[to\_string](../Topic/to_string.md)|値を `string` に変換します。|  
|[to\_wstring](../Topic/to_wstring.md)|値をワイド `string` に変換します。|  
  
### 関数  
  
|||  
|-|-|  
|[getline](../Topic/getline%20Template%20Function.md)|入力ストリームから文字列を行単位で抽出します。|  
  
### クラス  
  
|||  
|-|-|  
|[basic\_string クラス](../standard-library/basic-string-class.md)|文字に類する任意のオブジェクトのシーケンスを格納できるオブジェクトを記述するテンプレート クラス。|  
|[char\_traits 構造体](../standard-library/char-traits-struct.md)|CharType 型の文字に関連付けられている属性を記述するテンプレート クラス。|  
  
### 特殊化  
  
|||  
|-|-|  
|[char\_traits\<char\> 構造体](../standard-library/char-traits-char-struct.md)|テンプレート構造体 `char_traits`\<CharType\> を `char` 型の要素に特殊化した構造体。|  
|[char\_traits\<wchar\_t\> 構造体](../standard-library/char-traits-wchar-t-struct.md)|テンプレート構造体 `char_traits`\<CharType\> を `wchar_t` 型の要素に特殊化した構造体。|  
|[char\_traits\<char16\_t\> 構造体](../standard-library/char-traits-char16-t-struct.md)|テンプレート構造体 `char_traits`\<CharType\> を `char16_t` 型の要素に特殊化した構造体。|  
|[char\_traits\<char32\_t\> 構造体](../standard-library/char-traits-char32-t-struct.md)|テンプレート構造体 `char_traits`\<CharType\> を `char32_t` 型の要素に特殊化した構造体。|  
  
## 必要条件  
  
-   **ヘッダー:** \<string\>  
  
-   **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)