---
title: "regex_error クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex_error
- std::regex_error
- regex/std::regex_error
- std::regex_error::code
- regex/std::regex_error::code
dev_langs:
- C++
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: e5eab496a34eaef6f6d382ce8b1d10055c6b4422
ms.lasthandoff: 02/24/2017

---
# <a name="regexerror-class"></a>regex_error クラス
正しくない basic_regex オブジェクトを報告します。  
  
## <a name="syntax"></a>構文  
  
```  
class regex_error  
 : public std::runtime_error {  
public:  
    explicit regex_error(regex_constants::error_code error);

    regex_constants::error_code code() const;

 
 };  
```  
  
## <a name="remarks"></a>コメント  
 このクラスは、 `basic_regex` オブジェクトの構築時または使用時に発生したエラーを報告するためにスローされる例外オブジェクトを表します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<regex>  
  
 **名前空間:** std  
  
##  <a name="a-nameregexerrorcodea--regexerrorcode"></a><a name="regex_error__code"></a>  regex_error::code  
 エラー コードを返します。  
  
```  
regex_constants::error_code code() const;
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、オブジェクトのコンストラクターに渡された値を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// std__regex__regex_error_code.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex_error paren(std::regex_constants::error_paren);   
  
    try   
        {   
        std::regex rx("(a");   
        }   
    catch (const std::regex_error& rerr)   
        {   
        std::cout << "regex error: "   
            << (rerr.code() == paren.code()   
                 "unbalanced parentheses" : "")   
            << std::endl;   
        }   
    catch (...)   
        {   
        std::cout << "unknown exception" << std::endl;   
        }   
  
    return (0);   
    }  
  
```  
  
```Output  
regex error: unbalanced parentheses  
```  
  
##  <a name="a-nameregexerrorregexerrora--regexerrorregexerror"></a><a name="regex_error__regex_error"></a>  regex_error::regex_error  
 オブジェクトを構築します。  
  
```  
regex_error(regex_constants::error_code error);
```  
  
### <a name="parameters"></a>パラメーター  
 `error`  
 エラー コード。  
  
### <a name="remarks"></a>コメント  
 コンストラクターは、値 `error`を保持するオブジェクトを構築します。  
  
### <a name="example"></a>例  
  
```cpp  
// std__regex__regex_error_construct.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex_error paren(std::regex_constants::error_paren);   
  
    try   
        {   
        std::regex rx("(a");   
        }   
    catch (const std::regex_error& rerr)   
        {   
        std::cout << "regex error: "   
            << (rerr.code() == paren.code()   
                 "unbalanced parentheses" : "")   
            << std::endl;   
        }   
    catch (...)   
        {   
        std::cout << "unknown exception" << std::endl;   
        }   
  
    return (0);   
    }  
  
```  
  
```Output  
regex error: unbalanced parentheses  
```  
  
## <a name="see-also"></a>関連項目  
[\<regex>](../standard-library/regex.md)  
[regex_constants クラス](../standard-library/regex-constants-class.md)  
[\<regex> 系関数](../standard-library/regex-functions.md)  
[regex_iterator クラス](../standard-library/regex-iterator-class.md)  
[\<regex> 系演算子](../standard-library/regex-operators.md)  
[regex_token_iterator クラス](../standard-library/regex-token-iterator-class.md)  
[regex_traits クラス](../standard-library/regex-traits-class.md)  
[\<regex> typedefs](../standard-library/regex-typedefs.md)  

