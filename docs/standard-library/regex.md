---
title: "&lt;regex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<regex>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex ヘッダー [TR1]"
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# &lt;regex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[正規表現 \(C\+\+\)](../standard-library/regular-expressions-cpp.md)を解析するテンプレート クラスと、正規表現オブジェクトと一致するテキストを検索するいくつかのテンプレート クラスおよび関数を定義します。  
  
## 構文  
  
```  
#include <regex>  
```  
  
## 解説  
 正規表現オブジェクトを作成するには、[basic\_regex クラス](../Topic/basic_regex%20Class.md) テンプレート クラスを使用するか、これを特化した [regex Typedef](../Topic/regex%20Typedef.md) や [wregex Typedef](../Topic/wregex%20Typedef.md) を [regex\_constants::syntax\_option\_type](../Topic/regex_constants::syntax_option_type.md) 型の構文フラグと一緒に使用します。  
  
 正規表現オブジェクトと一致するテキストを検索するには、テンプレート関数 [regex\_match 関数](../Topic/regex_match%20Function.md) と [regex\_search 関数](../Topic/regex_search%20Function.md) を [regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md) 型の一致フラグと一緒に使用します。  これらの関数は、テンプレート クラス [match\_results クラス](../standard-library/match-results-class.md) と、これを特化した [cmatch Typedef](../Topic/cmatch%20Typedef.md)、[wcmatch Typedef](../Topic/wcmatch%20Typedef.md)、[smatch Typedef](../Topic/smatch%20Typedef.md)、および [wsmatch Typedef](../Topic/wsmatch%20Typedef.md) を、テンプレート クラス [sub\_match クラス](../standard-library/sub-match-class.md) と、これを特化した [csub\_match Typedef](../Topic/csub_match%20Typedef.md)、[wcsub\_match Typedef](../Topic/wcsub_match%20Typedef.md)、[ssub\_match Typedef](../Topic/ssub_match%20Typedef.md)、および [wssub\_match Typedef](../Topic/wssub_match%20Typedef.md) と一緒に使用して結果を返します。  
  
 正規表現オブジェクトと一致するテキストを置換するには、テンプレート関数 [regex\_replace 関数](../Topic/regex_replace%20Function.md) を [regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md) 型の一致フラグと一緒に使用します。  
  
 正規表現オブジェクトとの複数の一致を反復処理するには、テンプレート クラス [regex\_iterator クラス](../standard-library/regex-iterator-class.md) と [regex\_token\_iterator クラス](../Topic/regex_token_iterator%20Class.md) を使用するか、これらを特化した [cregex\_iterator Typedef](../Topic/cregex_iterator%20Typedef.md)、[sregex\_iterator Typedef](../Topic/sregex_iterator%20Typedef.md)、[wcregex\_iterator Typedef](../Topic/wcregex_iterator%20Typedef.md)、[wsregex\_iterator Typedef](../Topic/wsregex_iterator%20Typedef.md)、[cregex\_token\_iterator Typedef](../Topic/cregex_token_iterator%20Typedef.md)、[sregex\_token\_iterator Typedef](../Topic/sregex_token_iterator%20Typedef.md)、[wcregex\_token\_iterator Typedef](../Topic/wcregex_token_iterator%20Typedef.md)、または [wsregex\_token\_iterator Typedef](../Topic/wsregex_token_iterator%20Typedef.md) のいずれか 1 つを、[regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md) 型の一致フラグと一緒に使用します。  
  
 正規表現の文法の詳細を変更するには、正規表現の特徴を実装するクラスを記述します。  
  
### クラス  
  
|||  
|-|-|  
|[basic\_regex](../Topic/basic_regex%20Class.md)|正規表現をラップします。|  
|[match\_results](../standard-library/match-results-class.md)|サブマッチのシーケンスを保持します。|  
|[regex\_constants](../Topic/regex_constants%20Class.md)|各種の定数を保持します。|  
|[regex\_error](../standard-library/regex-error-class.md)|無効な正規表現を通知します。|  
|[regex\_iterator](../standard-library/regex-iterator-class.md)|一致した結果を反復処理します。|  
|[regex\_traits](../standard-library/regex-traits-class.md)|照合する要素の特性を記述します。|  
|[regex\_traits\<char\>](../standard-library/regex-traits-char-class.md)|照合する `char` の特性を記述します。|  
|[regex\_traits\<wchar\_t\>](../standard-library/regex-traits-wchar-t-class.md)|照合する `wchar_t` の特性を記述します。|  
|[regex\_token\_iterator](../Topic/regex_token_iterator%20Class.md)|サブマッチを反復処理します。|  
|[sub\_match](../standard-library/sub-match-class.md)|サブマッチを記述します。|  
  
### 型定義  
  
|||  
|-|-|  
|[cmatch](../Topic/cmatch%20Typedef.md)|`char` `match_results` の型定義。|  
|[cregex\_iterator](../Topic/cregex_iterator%20Typedef.md)|`char` `regex_iterator` の型定義。|  
|[cregex\_token\_iterator](../Topic/cregex_token_iterator%20Typedef.md)|`char` `regex_token_iterator` の型定義。|  
|[csub\_match](../Topic/csub_match%20Typedef.md)|`char` `sub_match` の型定義。|  
|[regex](../Topic/regex%20Typedef.md)|`char` `basic_regex` の型定義。|  
|[smatch](../Topic/smatch%20Typedef.md)|`string` `match_results` の型定義。|  
|[sregex\_iterator](../Topic/sregex_iterator%20Typedef.md)|`string` `regex_iterator` の型定義。|  
|[sregex\_token\_iterator](../Topic/sregex_token_iterator%20Typedef.md)|`string` `regex_token_iterator` の型定義。|  
|[ssub\_match](../Topic/ssub_match%20Typedef.md)|`string` `sub_match` の型定義。|  
|[wcmatch](../Topic/wcmatch%20Typedef.md)|`wchar_t` `match_results` の型定義。|  
|[wcregex\_iterator](../Topic/wcregex_iterator%20Typedef.md)|`wchar_t` `regex_iterator` の型定義。|  
|[wcregex\_token\_iterator](../Topic/wcregex_token_iterator%20Typedef.md)|`wchar_t` `regex_token_iterator` の型定義。|  
|[wcsub\_match](../Topic/wcsub_match%20Typedef.md)|`wchar_t` `sub_match` の型定義。|  
|[wregex](../Topic/wregex%20Typedef.md)|`wchar_t` `basic_regex` の型定義。|  
|[wsmatch](../Topic/wsmatch%20Typedef.md)|`wstring` `match_results` の型定義。|  
|[wsregex\_iterator](../Topic/wsregex_iterator%20Typedef.md)|`wstring` `regex_iterator` の型定義。|  
|[wsregex\_token\_iterator](../Topic/wsregex_token_iterator%20Typedef.md)|`wstring` `regex_token_iterator` の型定義。|  
|[wssub\_match](../Topic/wssub_match%20Typedef.md)|`wstring` `sub_match` の型定義。|  
  
### Functions  
  
|||  
|-|-|  
|[regex\_match](../Topic/regex_match%20Function.md)|正規表現と完全に一致します。|  
|[regex\_replace](../Topic/regex_replace%20Function.md)|一致した正規表現を置換します。|  
|[regex\_search](../Topic/regex_search%20Function.md)|正規表現との一致を検索します。|  
|[swap](../Topic/swap%20Function%20%3Cregex%3E.md)|`basic_regex` または `match_results` オブジェクトをスワップします。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\=\=](../Topic/operator==%20%3Cregex%3E.md)|さまざまなオブジェクトが等しいかどうかの比較|  
|[operator\!\=](../Topic/operator!=%20%3Cregex%3E.md)|さまざまなオブジェクトが等しくないかどうかの比較|  
|[\< 演算子](../Topic/operator%3C%20%3Cregex%3E.md)|さまざまなオブジェクトが他方より小さいかどうかの比較|  
|[\<\= 演算子](../Topic/operator%3C=%20%3Cregex%3E.md)|さまざまなオブジェクトが他方以下かどうかの比較|  
|[\> 演算子](../Topic/operator%3E%20%3Cregex%3E.md)|さまざまなオブジェクトが他方より大きいかどうかの比較|  
|[\>\= 演算子](../Topic/operator%3E=%20%3Cregex%3E.md)|さまざまなオブジェクトが他方以上かどうかの比較|  
|[演算子 \<\<](../Topic/operator%3C%3C%20%3Cregex%3E.md)|ストリームに `sub_match` を挿入します。|  
  
## 参照  
 [正規表現 \(C\+\+\)](../standard-library/regular-expressions-cpp.md)