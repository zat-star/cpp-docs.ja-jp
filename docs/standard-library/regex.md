---
title: '&lt;regex&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <regex>
dev_langs:
- C++
helpviewer_keywords:
- regex header
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 248e9ba676b906af62f6804f4939e04158a8e2ef
ms.openlocfilehash: 4e172f8bf72fd528027c333cf411a307aa97d786
ms.lasthandoff: 02/24/2017

---
# <a name="ltregexgt"></a>&lt;regex&gt;
[正規表現 (C++)](../standard-library/regular-expressions-cpp.md) を解析するテンプレート クラスと、正規表現オブジェクトに一致するテキストを検索するテンプレート クラスおよび関数を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <regex>  
```  
  
## <a name="remarks"></a>コメント  
 正規表現オブジェクトを作成するには、[basic_regex クラス](../standard-library/basic-regex-class.md) テンプレート クラスを使用するか、これを特化した [regex](../standard-library/regex-typedefs.md#regex_typedef) や [wregex](../standard-library/regex-typedefs.md#wregex_typedef) を [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#regex_constants__syntax_option_type) 型の構文フラグと一緒に使用します。  
  
 正規表現オブジェクトと一致するテキストを検索するには、テンプレート関数 [regex_match 関数](../standard-library/regex-functions.md#regex_match_function) や [regex_search 関数](../standard-library/regex-functions.md#regex_search_function) を [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#regex_constants__match_flag_type) 型の一致フラグと一緒に使用します。 これらの関数は、テンプレート クラス [match_results クラス](../standard-library/match-results-class.md) と、これを特化した [cmatch](../standard-library/regex-typedefs.md#cmatch_typedef)、[wcmatch](../standard-library/regex-typedefs.md#wcmatch_typedef)、[smatch](../standard-library/regex-typedefs.md#smatch_typedef)、および [wsmatch](../standard-library/regex-typedefs.md#wsmatch_typedef) を、テンプレート クラス [sub_match クラス](../standard-library/sub-match-class.md) と、これを特化した [csub_match](../standard-library/regex-typedefs.md#csub_match_typedef)、[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match_typedef)、[ssub_match](../standard-library/regex-typedefs.md#ssub_match_typedef)、および [wssub_match](../standard-library/regex-typedefs.md#wssub_match_typedef) と一緒に使用して結果を返します。  
  
 正規表現オブジェクトと一致するテキストを置換するには、テンプレート関数 [regex_replace 関数](../standard-library/regex-functions.md#regex_replace_function) を [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#regex_constants__match_flag_type) 型の一致フラグと一緒に使用します。  
  
 正規表現オブジェクトとの複数の一致を反復処理するには、テンプレート クラス [regex_iterator クラス](../standard-library/regex-iterator-class.md) と [regex_token_iterator クラス](../standard-library/regex-token-iterator-class.md) を使用するか、これらを特殊化した [cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator_typedef)、[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator_typedef)、[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator_typedef)、[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator_typedef)、[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator_typedef)、[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator_typedef)、[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator_typedef)、または [wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator_typedef) のいずれか&1; つを、[regex_constants::match_flag_type](../standard-library/regex-constants-class.md#regex_constants__match_flag_type) 型の一致フラグと一緒に使用します。  
  
 正規表現の文法の詳細を変更するには、正規表現の特徴を実装するクラスを記述します。  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[basic_regex](../standard-library/basic-regex-class.md)|正規表現をラップします。|  
|[match_results](../standard-library/match-results-class.md)|サブマッチのシーケンスを保持します。|  
|[regex_constants](../standard-library/regex-constants-class.md)|各種の定数を保持します。|  
|[regex_error](../standard-library/regex-error-class.md)|無効な正規表現を通知します。|  
|[regex_iterator](../standard-library/regex-iterator-class.md)|一致した結果を反復処理します。|  
|[regex_traits](../standard-library/regex-traits-class.md)|照合する要素の特性を記述します。|  
|[regex_traits\<char>](../standard-library/regex-traits-char-class.md)|照合する `char` の特性を記述します。|  
|[regex_traits<wchar_t>](../standard-library/regex-traits-wchar-t-class.md)|照合する `wchar_t` の特性を記述します。|  
|[regex_token_iterator](../standard-library/regex-token-iterator-class.md)|サブマッチを反復処理します。|  
|[sub_match](../standard-library/sub-match-class.md)|サブマッチを記述します。|  
  
### <a name="type-definitions"></a>型定義  
  
|||  
|-|-|  
|[cmatch](../standard-library/regex-typedefs.md#cmatch_typedef)|`char``match_results` の型定義。|  
|[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator_typedef)|`char``regex_iterator` の型定義。|  
|[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator_typedef)|`char``regex_token_iterator` の型定義。|  
|[csub_match](../standard-library/regex-typedefs.md#csub_match_typedef)|`char``sub_match` の型定義。|  
|[regex](../standard-library/regex-typedefs.md#regex_typedef)|`char``basic_regex` の型定義。|  
|[smatch](../standard-library/regex-typedefs.md#smatch_typedef)|`string``match_results` の型定義。|  
|[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator_typedef)|`string``regex_iterator` の型定義。|  
|[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator_typedef)|`string``regex_token_iterator` の型定義。|  
|[ssub_match](../standard-library/regex-typedefs.md#ssub_match_typedef)|`string``sub_match` の型定義。|  
|[wcmatch](../standard-library/regex-typedefs.md#wcmatch_typedef)|`wchar_t``match_results` の型定義。|  
|[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator_typedef)|`wchar_t``regex_iterator` の型定義。|  
|[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator_typedef)|`wchar_t``regex_token_iterator` の型定義。|  
|[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match_typedef)|`wchar_t``sub_match` の型定義。|  
|[wregex](../standard-library/regex-typedefs.md#wregex_typedef)|`wchar_t``basic_regex` の型定義。|  
|[wsmatch](../standard-library/regex-typedefs.md#wsmatch_typedef)|`wstring``match_results` の型定義。|  
|[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator_typedef)|`wstring``regex_iterator` の型定義。|  
|[wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator_typedef)|`wstring``regex_token_iterator` の型定義。|  
|[wssub_match](../standard-library/regex-typedefs.md#wssub_match_typedef)|`wstring``sub_match` の型定義。|  
  
### <a name="functions"></a>関数  
  
|||  
|-|-|  
|[regex_match](../standard-library/regex-functions.md#regex_match_function)|正規表現と完全に一致します。|  
|[regex_replace](../standard-library/regex-functions.md#regex_replace_function)|一致した正規表現を置換します。|  
|[regex_search](../standard-library/regex-functions.md#regex_search_function)|正規表現との一致を検索します。|  
|[swap](../standard-library/regex-functions.md#swap_function)|`basic_regex` または `match_results` オブジェクトをスワップします。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator==](../standard-library/regex-operators.md#operator_eq_eq)|さまざまなオブジェクトが等しいかどうかの比較|  
|[operator!=](../standard-library/regex-operators.md#operator_neq)|さまざまなオブジェクトが等しくないかどうかの比較|  
|[operator<](../standard-library/regex-operators.md#operator_lt_)|さまざまなオブジェクトが他方より小さいかどうかの比較|  
|[operator\<=](../standard-library/regex-operators.md#operator_lt__eq)|さまざまなオブジェクトが他方以下かどうかの比較|  
|[operator>](../standard-library/regex-operators.md#operator_gt_)|さまざまなオブジェクトが他方より大きいかどうかの比較|  
|[operator>=](../standard-library/regex-operators.md#operator_gt__eq)|さまざまなオブジェクトが他方以上かどうかの比較|  
|[operator<<](../standard-library/regex-operators.md#operator_lt__lt_)|ストリームに `sub_match` を挿入します。|  
  
## <a name="see-also"></a>関連項目  
[正規表現 (C++)](../standard-library/regular-expressions-cpp.md)  
[regex_constants クラス](../standard-library/regex-constants-class.md)  
[regex_error クラス](../standard-library/regex-error-class.md)  
[\<regex> 系関数](../standard-library/regex-functions.md)  
[regex_iterator クラス](../standard-library/regex-iterator-class.md)  
[\<regex> 系演算子](../standard-library/regex-operators.md)  
[regex_token_iterator クラス](../standard-library/regex-token-iterator-class.md)  
[regex_traits クラス](../standard-library/regex-traits-class.md)  
[\<regex> typedefs](../standard-library/regex-typedefs.md)  




