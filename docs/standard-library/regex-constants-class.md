---
title: "regex_constants クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex_constants
- regex/std::regex_constants
- error_collate
- regex/std::regex_constants::error_collate
- error_ctype
- regex/std::regex_constants::error_ctype
- error_escape
- regex/std::regex_constants::error_escape
- error_backref
- regex/std::regex_constants::error_backref
- error_brack
- regex/std::regex_constants::error_brack
- error_paren
- regex/std::regex_constants::error_paren
- error_brace
- regex/std::regex_constants::error_brace
- error_badbrace
- regex/std::regex_constants::error_badbrace
- error_range
- regex/std::regex_constants::error_range
- error_space
- regex/std::regex_constants::error_space
- error_badrepeat
- regex/std::regex_constants::error_badrepeat
- error_complexity
- regex/std::regex_constants::error_complexity
- error_stack
- regex/std::regex_constants::error_stack
- error_parse
- regex/std::regex_constants::error_parse
- error_syntax
- regex/std::regex_constants::error_syntax
- match_default
- regex/std::regex_constants::match_default
- match_not_bol
- regex/std::regex_constants::match_not_bol
- match_not_eol
- regex/std::regex_constants::match_not_eol
- match_not_bow
- regex/std::regex_constants::match_not_bow
- match_not_eow
- regex/std::regex_constants::match_not_eow
- match_any
- regex/std::regex_constants::match_any
- match_not_null
- regex/std::regex_constants::match_not_null
- match_continuous
- regex/std::regex_constants::match_continuous
- match_prev_avail
- regex/std::regex_constants::match_prev_avail
- format_default
- regex/std::regex_constants::format_default
- format_sed
- regex/std::regex_constants::format_sed
- format_no_copy
- regex/std::regex_constants::format_no_copy
- format_first_only
- regex/std::regex_constants::format_first_only
- regex/std::regex_constants::ECMAScript
- regex/std::regex_constants::basic
- regex/std::regex_constants::extended
- regex/std::regex_constants::awk
- regex/std::regex_constants::grep
- regex/std::regex_constants::egrep
- regex/std::regex_constants::icase
- regex/std::regex_constants::nosubs
- regex/std::regex_constants::optimize
- regex/std::regex_constants::collate
dev_langs:
- C++
helpviewer_keywords:
- regex_constants class
ms.assetid: 4a69c0ba-c46d-46e4-bd29-6f4efb805f26
caps.latest.revision: 18
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
ms.openlocfilehash: 9330a5c4e1b487880f405478dd7e8838af739c44
ms.lasthandoff: 02/24/2017

---
# <a name="regexconstants-class"></a>regex_constants クラス
正規表現フラグの名前空間です。  
  
## <a name="syntax"></a>構文  
  
```  
namespace regex_constants {  
    enum syntax_option_type;  
    enum match_flag_type;  
    enum error_type;  
 }  
```  
  
## <a name="remarks"></a>コメント  
 `regex_constants` 名前空間は、各種のフラグおよび関連するフラグ値をカプセル化します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<regex>  
  
 **名前空間:** std  
  
##  <a name="regex_constants__error_type"></a>  regex_constants::error_type  
 正規表現の構文エラーを報告するためのフラグです。  
  
```  
enum error_type
    {    // identify error
    error_collate,
    error_ctype,
    error_escape,
    error_backref,
    error_brack,
    error_paren,
    error_brace,
    error_badbrace,
    error_range,
    error_space,
    error_badrepeat,
    error_complexity,
    error_stack,
    error_parse,
    error_syntax
    };  
```  
  
### <a name="remarks"></a>コメント  
 この型は、エラー フラグを保持できるオブジェクトを表す列挙型です。 次に、それぞれのフラグ値を示します。  
  
 `error_backref` -- 式に正しくない前方参照が存在する  
  
 `error_badbrace` -- 式が { } 式に正しくない回数を含んでいる  
  
 `error_badrepeat` -- 繰り返し式 (一般に、'*'、''、'+'、'{' のいずれか) の前に式が指定されていない  
  
 `error_brace` -- 式で '{' または '}' の対応が正しくない  
  
 `error_brack` -- 式で '[' または ']' の対応が正しくない  
  
 `error_collate` -- 式に正しくない照合要素名が存在する  
  
 `error_complexity` -- 検索式が複雑すぎるために失敗した  
  
 `error_ctype` -- 式に正しくない文字クラス名が存在する  
  
 `error_escape` -- 式に正しくないエスケープ シーケンスが存在する  
  
 `error_paren` -- 式で '(' または ')' の対応が正しくない  
  
 `error_parse` -- 式の解析に失敗した  
  
 `error_range` -- 式に正しくない文字範囲指定子が存在する  
  
 `error_space` -- リソース不足が原因で正規表現の解析に失敗した  
  
 `error_stack` -- メモリ不足が原因で検索に失敗した  
  
 `error_syntax` -- 構文エラーが原因で解析に失敗した  
  
 `error_backref` -- 式に正しくない前方参照が存在する  
  
##  <a name="regex_constants__match_flag_type"></a>  regex_constants::match_flag_type  
 正規表現照合オプションのフラグ。  
  
```  
enum match_flag_type 
    {    // specify matching and formatting rules
    match_default = 0x0000,
    match_not_bol = 0x0001,
    match_not_eol = 0x0002,
    match_not_bow = 0x0004,
    match_not_eow = 0x0008,
    match_any = 0x0010,
    match_not_null = 0x0020,
    match_continuous = 0x0040,
    match_prev_avail = 0x0100,
    format_default = 0x0000,
    format_sed = 0x0400,
    format_no_copy = 0x0800,
    format_first_only = 0x1000,
    _Match_not_null = 0x2000
    };  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テキスト シーケンスを正規表現に照らして照合するときに使用されるオプションと、テキストを置き換えるときに使用される書式設定フラグを表すビットマスク型です。 オプションは `|`を使用して連結できます。  
  
 照合オプションは次のとおりです。  
  
 `match_default`  
  
 `match_not_bol` - ターゲット シーケンス内の先頭の位置を行の始まりとして処理しません  
  
 `match_not_eol` - ターゲット シーケンス内の末尾の次の位置を行の終わりとして処理しません  
  
 `match_not_bow` - ターゲット シーケンス内の先頭の位置を単語の始まりとして処理しません  
  
 `match_not_eow` - ターゲット シーケンス内の末尾の次の位置を単語の終わりとして処理しません  
  
 `match_any` - 複数の一致が可能な場合は、すべての一致が受け入れられます  
  
 `match_not_null` - 空のサブシーケンスを一致として処理しません  
  
 `match_continuous` - ターゲット シーケンスの先頭以外で一致を検索しません  
  
 `match_prev_avail` -- `--first` は正しい反復子です。`match_not_bol` と `match_not_bow` は設定されている場合に無視されます  
  
 書式指定フラグは次のとおりです。  
  
 `format_default` -- ECMAScript 書式規則を使用します  
  
 `format_sed` -- sed 書式規則を使用します  
  
 `format_no_copy` -- 正規表現と一致しないテキストをコピーしません  
  
 `format_first_only` -- 最初の一致の後は一致を検索しません  
  
##  <a name="regex_constants__syntax_option_type"></a>  regex_constants::syntax_option_type  
 構文オプションを選択するためのフラグ。  
  
```  
enum syntax_option_type
    {    // specify RE syntax rules
    ECMAScript = 0x01,
    basic = 0x02,
    extended = 0x04,
    awk = 0x08,
    grep = 0x10,
    egrep = 0x20,
    _Gmask = 0x3F,

    icase = 0x0100,
    nosubs = 0x0200,
    optimize = 0x0400,
    collate = 0x0800
    };  
```  
  
### <a name="remarks"></a>コメント  
 この型は、正規表現をコンパイルするときに使用される言語指定子と構文修飾子を表すビットマスク型です。 オプションは `|`を使用して連結できます。 一度に使用できる言語指定子は&1; つだけです。  
  
 言語指定子は次のとおりです。  
  
 `ECMAScript` -- ECMAScript としてコンパイルします  
  
 `basic` -- BRE としてコンパイルします  
  
 `extended` -- ERE としてコンパイルします  
  
 `awk` -- awk としてコンパイルします  
  
 `grep` -- grep としてコンパイルします  
  
 `egrep` -- egrep としてコンパイルします  
  
 構文修飾子は次のとおりです。  
  
 `icase` -- 一致で大文字と小文字を区別しません  
  
 `nosubs` -- 実装でキャプチャ グループの内容を追跡する必要がありません  
  
 `optimize` -- 実装で正規表現のコンパイル速度よりも、照合の速度を重視する必要があります  
  
 `collate` -- 一致でロケールを区別します  
  
## <a name="see-also"></a>関連項目  
[\<regex>](../standard-library/regex.md)  
[regex_error クラス](../standard-library/regex-error-class.md)  
[\<regex> 系関数](../standard-library/regex-functions.md)  
[regex_iterator クラス](../standard-library/regex-iterator-class.md)  
[\<regex> 系演算子](../standard-library/regex-operators.md)  
[regex_token_iterator クラス](../standard-library/regex-token-iterator-class.md)  
[regex_traits クラス](../standard-library/regex-traits-class.md)  
[\<regex> typedefs](../standard-library/regex-typedefs.md)  

