---
title: "__declspec | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__declspec_cpp"
  - "__declspec"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec キーワード [C++]"
ms.assetid: 832db681-e8e1-41ca-b78c-cd9d265cdb87
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __declspec
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 ストレージ クラス情報を指定するための拡張属性構文は、`__declspec` キーワードを使用します。指定した型のインスタンスは、このキーワードに指定した Microsoft 固有のストレージ クラス属性 \(以降の一覧を参照\) を付けて保存されます。  他のストレージ クラス修飾子の例としては、`static` および `extern` キーワードがあります。  ただし、これらのキーワードは C および C\+\+ 言語の ANSI 仕様の一部であるため、拡張属性構文では扱われません。  拡張属性構文は、Microsoft 固有の C および C\+\+ 言語拡張を簡略化し、標準化します。  
  
## 文法  
 *decl\-specifier*:  
 `__declspec (`  *extended\-decl\-modifier\-seq*  `)`  
  
 *extended\-decl\-modifier\-seq*:  
 *extended\-decl\-modifier* opt  
  
 *extended\-decl\-modifier extended\-decl\-modifier\-seq*  
  
 *extended\-decl\-modifier*:  
 `align(` *\#* `)`  
  
 `allocate("` *segname* `")`  
  
 `appdomain`  
  
 `code_seg("` *segname* `")`  
  
 `deprecated`  
  
 `dllimport`  
  
 `dllexport`  
  
 `jitintrinsic`  
  
 `naked`  
  
 `noalias`  
  
 `noinline`  
  
 `noreturn`  
  
 `nothrow`  
  
 `novtable`  
  
 `process`  
  
 `property(`{`get=`*get\_func\_name*&#124;`,put=`*put\_func\_name*}`)`  
  
 `restrict`  
  
 `safebuffers`  
  
 `selectany`  
  
 `thread`  
  
 `uuid("` *ComObjectGUID* `")`  
  
 空白は、宣言修飾子のシーケンスを区切ります。  その例は以降のセクションで示します。  
  
 拡張属性の文法は、次の Microsoft 固有のストレージ クラス属性をサポートしています。[align](../cpp/align-cpp.md)、[allocate](../Topic/allocate.md)、[appdomain](../Topic/appdomain.md)、[code\_seg](../cpp/code-seg-declspec.md)、[deprecated](../cpp/deprecated-cpp.md)、[dllexport](../cpp/dllexport-dllimport.md)、[dllimport](../cpp/dllexport-dllimport.md)、[jitintrinsic](../cpp/jitintrinsic.md)、[naked](../Topic/naked%20\(C++\).md)、[noalias](../cpp/noalias.md)、[noinline](../cpp/noinline.md)、[noreturn](../cpp/noreturn.md)、[nothrow](../Topic/nothrow%20\(C++\).md)、[novtable](../cpp/novtable.md)、[process](../cpp/process.md)、[restrict](../cpp/restrict.md)、[safebuffers](../Topic/safebuffers.md)、[selectany](../cpp/selectany.md)、[thread](../cpp/thread.md)。  また、次の COM オブジェクトの属性もサポートしています。[property](../cpp/property-cpp.md)、[uuid](../cpp/uuid-cpp.md)。  
  
 `code_seg`、`dllexport`、`dllimport`、`naked`、`noalias`、`nothrow`、`property`、`restrict`、`selectany`、`thread`、 `uuid` の各ストレージ クラス属性は、適用先のオブジェクトまたは関数の宣言のみのプロパティです。  `thread` 属性はデータとオブジェクトにのみ影響を与えます。  `naked` 属性は関数にのみ影響を与えます。  `dllimport` および `dllexport` 属性は関数、データ、オブジェクトに影響を与えます。  `property`、`selectany`、および `uuid` 属性は COM オブジェクトに影響を与えます。  
  
 `__declspec` キーワードは単純な宣言の先頭に置く必要があります。  コンパイラは警告なしに、宣言内で \* または & の後、変数識別子の前に置かれた `__declspec` キーワードを無視します。  
  
 ユーザー定義型の宣言の先頭で指定された `__declspec` 属性は、その型の変数に適用されます。  次に例を示します。  
  
```  
__declspec(dllimport) class X {} varX;  
```  
  
 この場合、属性は `varX` に適用されます。  `class` または `struct` キーワードの後に置かれた `__declspec` 属性はユーザー定義の型に適用されます。  次に例を示します。  
  
```  
class __declspec(dllimport) X {};  
```  
  
 この場合、属性は `X` に適用されます。  
  
 単純な宣言に `__declspec` 属性を使用するための一般的なガイドラインは次のとおりです。  
  
```  
  
decl-specifier-seq declarator-list;  
```  
  
 *decl\-specifier\-seq* には特に、基本型 \(  `int`、`float`、`typedef`、クラス名など\)、ストレージ クラス \(  `static`、`extern` など\)、または `__declspec` 拡張属性を含める必要があります。  *init\-declarator\-list* には特に、宣言のポインターの一部を含める必要があります。  次に例を示します。  
  
```  
__declspec(selectany) int * pi1 = 0;   //OK, selectany & int both part of decl-specifier  
int __declspec(selectany) * pi2 = 0;   //OK, selectany & int both part of decl-specifier  
int * __declspec(selectany) pi3 = 0;   //ERROR, selectany is not part of a declarator  
```  
  
 次のコードでは、整数型のスレッド ローカル変数を宣言して特定の値に初期化します。  
  
```  
// Example of the __declspec keyword  
__declspec( thread ) int tls_i = 1;  
```  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [C 拡張ストレージ クラス属性](../c-language/c-extended-storage-class-attributes.md)