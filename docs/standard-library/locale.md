---
title: "&lt;locale&gt; | Microsoft Docs"
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
  - "<locale>"
  - "std.<locale>"
  - "locale/std::<locale>"
  - "std::<locale>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "locale ヘッダー"
ms.assetid: ca56f9d2-7128-44da-8df1-f4c78c17fbf2
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;locale&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

文字分類と文字列の照合順序の国際化サポートを含む、数値、通貨、暦のデータの表示や書式設定に関するさまざまな文化的慣習をカプセル化および操作するために、C\+\+ プログラムで使用できるテンプレート クラスおよび関数を定義します。  
  
## 構文  
  
```  
  
#include <locale>  
  
```  
  
### Functions  
  
|||  
|-|-|  
|[has\_facet](../Topic/has_facet.md)|特定のファセットが指定されたロケールに格納されているかどうかをテストします。|  
|[isalnum](../Topic/isalnum.md)|ロケールの要素が英字または数字であるかどうかをテストします。|  
|[isalpha](../Topic/isalpha.md)|ロケールの要素が英字であるかどうかをテストします。|  
|[iscntrl](../Topic/iscntrl.md)|ロケールの要素が制御文字であるかどうかをテストします。|  
|[isdigit](../Topic/isdigit.md)|ロケールの要素が数字であるかどうかをテストします。|  
|[isgraph](../Topic/isgraph.md)|ロケールの要素が英字または句読点であるかどうかをテストします。|  
|[islower](../Topic/islower.md)|ロケールの要素が小文字であるかどうかをテストします。|  
|[isprint](../Topic/isprint.md)|ロケールの要素が印刷可能な文字であるかどうかをテストします。|  
|[ispunct](../Topic/ispunct.md)|ロケールの要素が句読点であるかどうかをテストします。|  
|[isspace](../Topic/isspace.md)|ロケールの要素が空白文字であるかどうかをテストします。|  
|[isupper](../Topic/isupper.md)|ロケールの要素が大文字であるかどうかをテストします。|  
|[isxdigit](../Topic/isxdigit.md)|ロケールの要素が 16 進数を表すために使用される文字であるかどうかをテストします。|  
|[tolower](../Topic/tolower.md)|文字を小文字に変換します。|  
|[toupper](../Topic/toupper.md)|文字を大文字に変換します。|  
|[use\_facet](../Topic/use_facet.md)|ロケールに格納されている指定された型のファセットへの参照を返します。|  
  
### クラス  
  
|||  
|-|-|  
|[codecvt](../standard-library/codecvt-class.md)|内部と外部の文字エンコーディングの変換に使用されるファセットを提供するテンプレート クラス。|  
|[codecvt\_base](../standard-library/codecvt-base-class.md)|変換の結果を示すためにファセットのメンバー関数の戻り値の型として使用される、**result** と呼ばれる列挙型を定義するために使用される codecvt クラスの基底クラス。|  
|[codecvt\_byname](../Topic/codecvt_byname%20Class.md)|特定のロケールの照合ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。変換に関する文化的領域に固有の情報を取得できるようにします。|  
|[collate](../standard-library/collate-class.md)|文字列の並べ替え規則を処理するためのファセットを提供する照合テンプレート クラス。|  
|[collate\_byname](../Topic/collate_byname%20Class.md)|特定のロケールの照合ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。文字列の並べ替え規則に関する文化的領域に固有の情報を取得できるようにします。|  
|[ctype](../standard-library/ctype-class.md)|文字の分類、大文字と小文字の変換、およびネイティブ文字セットとロケールで使用される文字セットとの変換に使用されるファセットを提供するテンプレート クラス。|  
|[ctype\<char\>](../standard-library/ctype-char-class.md)|`char` 型への **ctype\<CharType\>** テンプレート クラスの明示的な特殊化クラス。`char` 型の文字のさまざまなプロパティを設定するロケール ファセットとして使用できるオブジェクトを表します。|  
|[ctype\_base](../standard-library/ctype-base-class.md)|個々の文字または範囲全体の文字を分類またはテストするための列挙型を定義するために使用される ctype クラスの基底クラス。|  
|[ctype\_byname](../standard-library/ctype-byname-class.md)|特定のロケールの ctype ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。文字の分類や、大文字と小文字およびネイティブと指定されたロケールの文字セットでの文字の変換を実行できるようにします。|  
|[ロケール](../standard-library/locale-class.md)|特定のローカライズされた環境を集合的に定義する一連のファセットとして、カルチャ固有の情報をカプセル化するロケール オブジェクトを表すクラス。|  
|[メッセージ](../standard-library/messages-class.md)|このテンプレート クラスは、特定のロケールの国際化メッセージのカタログからローカライズされたメッセージを取得するためにロケールのファセットとして使用できるオブジェクトを表します。|  
|[messages\_base](../Topic/messages_base%20Class.md)|メッセージのカタログの `int` 型を表す基底クラス。|  
|[messages\_byname](../standard-library/messages-byname-class.md)|特定のロケールのメッセージ ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。ローカライズされたメッセージを取得できるようにします。|  
|[money\_base](../Topic/money_base%20Class.md)|個々の文字または範囲全体の文字を分類またはテストするための列挙型を定義するために使用される ctype クラスの基底クラス。|  
|[money\_get](../standard-library/money-get-class.md)|**CharType** 型のシーケンスから通貨値への変換を制御するためにロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。|  
|[money\_put](../standard-library/money-put-class.md)|通貨値から **CharType** 型のシーケンスへの変換を制御するためにロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。|  
|[moneypunct](../Topic/moneypunct%20Class.md)|通貨入力フィールドまたは通貨出力フィールドを表すために使用される **CharType** 型のシーケンスを表すロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。|  
|[moneypunct\_byname](../standard-library/moneypunct-byname-class.md)|特定のロケールの moneypunct ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。通貨の入力または出力フィールドを書式設定できるようにします。|  
|[num\_get](../Topic/num_get%20Class.md)|**CharType** 型のシーケンスから数値への変換を制御するためにロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。|  
|[num\_put](../standard-library/num-put-class.md)|数値から **CharType** 型のシーケンスへの変換を制御するためにロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。|  
|[numpunct](../standard-library/numpunct-class.md)|数値とブール式の書式設定および区切りに関する情報を表すために使用される、**CharType** 型のシーケンスを表すロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。|  
|[numpunct\_byname](../standard-library/numpunct-byname-class.md)|特定のロケールの moneypunct ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。数値とブール式の書式設定および区切りを有効にします。|  
|[time\_base](../Topic/time_base%20Class.md)|time\_get テンプレート クラスのファセットの基底クラスとして使用されるクラス。dateorder 列挙型とこの方の複数の定数のみを定義します。|  
|[time\_get](../standard-library/time-get-class.md)|**CharType** 型のシーケンスから時刻値への変換を制御するためにロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。|  
|[time\_get\_byname](../standard-library/time-get-byname-class.md)|time\_get\<**CharType**, **InputIterator**\> 型のロケール ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。|  
|[time\_put](../standard-library/time-put-class.md)|時刻値から **CharType** 型のシーケンスへの変換を制御するためにロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。|  
|[time\_put\_byname](../standard-library/time-put-byname-class.md)|`time_put`\<**CharType**, **OutputIterator**\> 型のロケール ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。|  
|[wbuffer\_convert クラス](../standard-library/wbuffer-convert-class.md)|バイト ストリーム バッファーとの間の要素の転送を制御するストリーム バッファーを説明します。|  
|[wstring\_convert クラス](../standard-library/wstring-convert-class.md)|ワイド文字列とバイト文字列間の変換を実行するテンプレート クラス。|  
  
## 参照  
 [コード ページ](../c-runtime-library/code-pages.md)   
 [ロケール名、言語、および国\/地域識別文字列](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)