---
title: "regex_traits クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "regex_traits"
  - "std::tr1::regex_traits"
  - "std.tr1.regex_traits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_traits クラス [TR1]"
ms.assetid: bc5a5eed-32fc-4eb7-913d-71c42e729e81
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# regex_traits クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

照合する要素の特性を記述します。  
  
## 構文  
  
```  
template<class Elem>  
    struct regex_traits {  
    regex_traits();  
  
    static size_type length(const char_type *str);  
    char_type translate(char_type ch) const;  
    char_type translate_nocase(char_type ch) const;  
    template<class FwdIt>  
        string_type transform(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        string_type transform_primary(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        char_class_type lookup_classname(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        string_type lookup_collatename(FwdIt first, FwdIt last) const;  
    bool isctype(char_type ch, char_class_type cls) const;  
    int value(Elem ch, int base) const;  
    locale_type imbue(locale_type loc);  
    locale_type getloc() const;  
  
    typedef Elem char_type;  
    typedef T6 size_type;  
    typedef basic_string<Elem> string_type;  
    typedef T7 locale_type;  
    typedef T8 char_class_type;  
    };  
```  
  
#### パラメーター  
 `Elem`  
 記述する要素の型。  
  
## 解説  
 このテンプレート クラスは、`Elem` 型のさまざまな正規表現の特徴 \(traits\) を表します。 テンプレート クラス [basic\_regex クラス](../Topic/basic_regex%20Class.md) では、この情報を使用して、`Elem` 型の要素を操作します。  
  
 各 `regex_traits` オブジェクトは、そのオブジェクトの一部のメンバー関数が使用する `regex_traits::locale` 型のオブジェクトを保持します。 既定のロケールは、`regex_traits::locale()` のコピーです。 メンバー関数 `imbue` は、ロケール オブジェクトを置き換えます。また、メンバー関数 `getloc` は、ロケール オブジェクトのコピーを返します。  
  
## 必要条件  
 **ヘッダー:** \<regex\>  
  
 **名前空間:** std  
  
## 参照  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_traits](../standard-library/regex-traits-class.md)   
 [regex\_traits \< char \> クラス](../standard-library/regex-traits-char-class.md)   
 [regex\_traits\<wchar\_t\> クラス](../standard-library/regex-traits-wchar-t-class.md)