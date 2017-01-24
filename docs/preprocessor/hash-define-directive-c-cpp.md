---
title: "#define ディレクティブ (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#define"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#define ディレクティブ"
  - "#define ディレクティブ, 構文"
  - "define ディレクティブ (#define)"
  - "define ディレクティブ (#define), 構文"
  - "プリプロセッサ, ディレクティブ"
ms.assetid: 33cf25c6-b24e-40bf-ab30-9008f0391710
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #define ディレクティブ (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`#define` は、識別子またはパラメーター化された識別子とトークン文字列との関連付けである、*マクロ*を作成します。  マクロが定義されると、コンパイラはそれ以降にソース ファイル内に識別子が見つかるたびに、トークン文字列に置き換えることができます。  
  
## 構文  
 `#define` *identifier* *token\-string*opt  
  
 `#define` *identifier*`(` *identifier*opt`,` *...* `,` *identifier*opt `)` *token\-string*opt  
  
## 解説  
 `#define` ディレクティブにより、コンパイラはソース ファイル内に *identifier* が見つかるたびに、*token\-string* に置き換えます。  *identifier* は、それがトークンを形成する場合のみ、置き換えられます。  つまり、*identifier* は、コメント内、文字列内、または長い識別子の一部として見つかった場合、置き換えられません。  詳細については、「[C\+\+ トークン](../cpp/tokens-cpp.md)」を参照してください。  
  
 *token\-string* 引数は、キーワード、定数、完全なステートメントなどの一連のトークンで構成されます。  1 つ以上の空白文字を使用して *token\-string* と *identifier* を区切る必要があります。  この空白は、置き換えられるテキストの一部とは見なされません。最後のトークンのテキストに続く空白も同様です。  
  
 `#define` に *token\-string* がないと、ソース ファイルから *identifier* が削除されます。  *identifier* を定義したまま、`#if defined` ディレクティブと `#ifdef` ディレクティブを使用してテストできます。  
  
 2 番目の構文形式は、パラメーターを受け取る関数に似たマクロを定義します。  この形式では、かっこで囲んだパラメーターのリストを使用できます \(省略可能\)。  このマクロが定義されると、それ以降に *identifier*\( *identifier*opt, ..., *identifier*opt \) が見つかるたびに、仮パラメーターが実引数に置き換わった *token\-string* に置き換わります。  
  
 仮パラメーターの名前は *token\-string* に含まれ、実際の値が代入される場所を示します。  各パラメーター名は、*token\-string* 内に任意の順序で複数回含めることができます。  呼び出しにある引数の数は、マクロ定義にあるパラメーターの数に一致する必要があります。  かっこを多めに使用することで、複雑な実引数が正しく解釈されるようにできます。  
  
 リスト内で仮パラメーターはコンマで区切ります。  リストの各名前は一意である必要があり、リストはかっこで囲む必要があります。  空白を *identifier* と左かっこの間に挿入することはできません。  複数のソース行にまたがる長いディレクティブには行の連結を使用します \(改行文字の直前に円記号 \(`\`\) を挿入します\)。  仮パラメーター名のスコープは、*token\-string* で終了する新しい行まで拡張されます。  
  
 マクロが 2 番目の構文形式で定義されると、それ以降の引数リストまでのテキスト インスタンスがマクロの呼び出しを示します。  ソース ファイル内の *identifier* のインスタンスに続く実引数は、マクロ定義内の対応する仮パラメーターと対になります。  文字列化演算子 \(`#`\)、文字定数化演算子 \(`#@`\)、またはトークン連結演算子 \(`##`\) が前置されていないか、`##` 演算子が後置されていない *token\-string* の各仮パラメーターは、対応する実引数に置き換えられます。  ディレクティブが仮パラメーターを置き換える前に、実引数内のすべてのマクロが展開されます  \(演算子については「[プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)」を参照\)。  
  
 引数を受け取るマクロの次の例では、`#define` の 2 番目の構文形式を示しています。  
  
```  
// Macro to define cursor lines   
#define CURSOR(top, bottom) (((top) << 8) | (bottom))  
  
// Macro to get a random integer with a specified range   
#define getrandom(min, max) \  
    ((rand()%(int)(((max) + 1)-(min)))+ (min))  
```  
  
 副作用のある引数が原因で、マクロが予期しない結果を生成することがあります。  同じ仮パラメーターが *token\-string* に複数回含まれている場合があります。  その仮パラメーターが副作用のある式と置き換えられると、その式は、その副作用と共に、複数回評価される場合があります  \(「[トークン連結演算子 \(\#\#\)](../preprocessor/token-pasting-operator-hash-hash.md)」の例を参照\)。  
  
 `#undef` ディレクティブは、識別子のプリプロセッサ定義を未定義の状態にします。  詳細については、「[\#undef ディレクティブ](../preprocessor/hash-undef-directive-c-cpp.md)」を参照してください。  
  
 定義されているマクロの名前が *token\-string* に見つかった場合 \(別のマクロの展開の結果であっても\)、この名前は展開されません。  
  
 同じ名前のマクロの 2 番目の `#define` は、2 番目のトークン シーケンスが最初のものと同じでなければ、警告を生成します。  
  
 **Microsoft 固有の仕様 →**  
  
 Microsoft C\/C\+\+ では、新しい定義が元の定義と構文的に同一の場合、マクロを再定義できます。  つまり、2 つの定義に異なるパラメーター名を付けることができます。  この動作は、2 つの定義が語彙的に同一である必要がある [!INCLUDE[vcpransi](../preprocessor/includes/vcpransi_md.md)] C とは異なります。  
  
 たとえば、次の 2 つのマクロは、パラメーター名を除いて同一です。  [!INCLUDE[vcpransi](../preprocessor/includes/vcpransi_md.md)] C ではこのような再定義はできませんが、Microsoft C\/C\+\+ ではエラーなしでコンパイルされます。  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( a1 * a2 )  
```  
  
 一方、次の 2 つのマクロは同一ではなく、Microsoft C\/C\+\+ で警告が生成されます。  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( b1 * b2 )  
```  
  
 **END Microsoft 固有の仕様**  
  
 `#define` ディレクティブの例を次に示します。  
  
```  
#define WIDTH       80  
#define LENGTH      ( WIDTH + 10 )  
```  
  
 最初のステートメントは識別子 `WIDTH` を整数定数 80 として定義し、`WIDTH` と整数定数 10 に基づき `LENGTH` を定義します。  `LENGTH` は見つかるたびに \(`WIDTH + 10`\) に置き換えられます。  次に、`WIDTH + 10` は見つかるたびに式 \(`80 + 10`\) に置き換えられます。  `WIDTH + 10` を囲むかっこは、次のようなステートメントの解釈を制御するため重要です。  
  
```  
var = LENGTH * 20;  
```  
  
 プロプロセス段階が終了すると、ステートメントは次のようになります。  
  
```  
var = ( 80 + 10 ) * 20;  
```  
  
 1800 に評価されます。  かっこがない場合、結果は次のようになります。  
  
```  
var = 80 + 10 * 20;  
```  
  
 280 に評価されます。  
  
 **Microsoft 固有の仕様 →**  
  
 [\/D](../build/reference/d-preprocessor-definitions.md) コンパイラ オプションを使用したマクロおよび定数の定義は、ファイルの先頭に `#define` プリプロセス ディレクティブを使用する場合と同じ結果になります。  \/D オプションを使用して最大 30 個のマクロを定義できます。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)