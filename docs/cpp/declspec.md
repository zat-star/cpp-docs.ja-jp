---
title: "_ _declspec |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __declspec_cpp
- __declspec
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++]
ms.assetid: 832db681-e8e1-41ca-b78c-cd9d265cdb87
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: b29b6243611f1ca59a579869469c803d3735f9df
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="declspec"></a>__declspec
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 ストレージ クラス情報を指定するための拡張属性構文は、`__declspec` キーワードを使用します。指定した型のインスタンスは、このキーワードに指定した Microsoft 固有のストレージ クラス属性 (以降の一覧を参照) を付けて保存されます。 他のストレージ クラス修飾子の例としては、`static` および `extern` キーワードがあります。 ただし、これらのキーワードは C および C++ 言語の ANSI 仕様の一部であるため、拡張属性構文では扱われません。 拡張属性構文は、Microsoft 固有の C および C++ 言語拡張を簡略化し、標準化します。  
  
## <a name="grammar"></a>文法  
 *宣言指定子*:  
 `__declspec (`  *拡張修飾子 decl-seq*  `)`  
  
 *extended-decl-modifier-seq*:  
 *extended-decl-modifier*opt  
  
 *拡張 decl 修飾子拡張 decl-修飾子--seq*  
  
 *extended-decl-modifier*:  
 `align(` *#* `)`  
  
 `allocate("`*segname*`")`  
  
 `appdomain`  
  
 `code_seg("`*segname*`")`  
  
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
  
 `property(`{`get=`*get_func_name*&#124;`,put=`*put_func_name*}`)`  
  
 `restrict`  
  
 `safebuffers`  
  
 `selectany`  
  
 `thread`  
  
 `uuid("`*ComObjectGUID*`")`  
  
 空白は、宣言修飾子のシーケンスを区切ります。 その例は以降のセクションで示します。  
  
 拡張属性の文法は、これらの Microsoft 固有ストレージ クラス属性をサポートしています:[整列](../cpp/align-cpp.md)、[割り当てる](../cpp/allocate.md)、 [appdomain](../cpp/appdomain.md)、 [code_seg](../cpp/code-seg-declspec.md)、[廃止](../cpp/deprecated-cpp.md)、 [dllexport](../cpp/dllexport-dllimport.md)、 [dllimport](../cpp/dllexport-dllimport.md)、 [jitintrinsic](../cpp/jitintrinsic.md)、 [naked](../cpp/naked-cpp.md)、 [noalias](../cpp/noalias.md)、 [noinline](../cpp/noinline.md)、 [noreturn](../cpp/noreturn.md)、 [nothrow](../cpp/nothrow-cpp.md)、 [novtable](../cpp/novtable.md)、[プロセス](../cpp/process.md)、[制限](../cpp/restrict.md)、 [safebuffers](../cpp/safebuffers.md)、 [selectany](../cpp/selectany.md)、および[スレッド](../cpp/thread.md)です。 これらの COM オブジェクト属性もサポートしています:[プロパティ](../cpp/property-cpp.md)と[uuid](../cpp/uuid-cpp.md)です。  
  
 `code_seg`、`dllexport`、`dllimport`、`naked`、`noalias`、`nothrow`、`property`、`restrict`、`selectany`、`thread`、 `uuid` の各ストレージ クラス属性は、適用先のオブジェクトまたは関数の宣言のみのプロパティです。 `thread` 属性はデータとオブジェクトにのみ影響を与えます。 `naked` 属性は関数にのみ影響を与えます。 `dllimport` および `dllexport` 属性は関数、データ、オブジェクトに影響を与えます。 `property`、`selectany`、および `uuid` 属性は COM オブジェクトに影響を与えます。  
  
 `__declspec` キーワードは単純な宣言の先頭に置く必要があります。 コンパイラは警告なしに、宣言内で * または & の後、変数識別子の前に置かれた `__declspec` キーワードを無視します。  
  
 ユーザー定義型の宣言の先頭で指定された `__declspec` 属性は、その型の変数に適用されます。 例:  
  
```  
__declspec(dllimport) class X {} varX;  
```  
  
 この場合、属性は `varX` に適用されます。 `__declspec` または `class` キーワードの後に置かれた `struct` 属性はユーザー定義の型に適用されます。 例:  
  
```  
class __declspec(dllimport) X {};  
```  
  
 この場合、属性は `X` に適用されます。  
  
 単純な宣言に `__declspec` 属性を使用するための一般的なガイドラインは次のとおりです。  
  
```  
  
decl-specifier-seq  
declarator-list;  
```  
  
 *Decl-seq 指定子*含めることは、特に、基本型 (例: `int`、 `float`、 `typedef`、またはクラス名)、ストレージ クラス (例: `static`、 `extern`)、または、 `__declspec`拡張機能です。 *Init 宣言子リスト*を含めることは、特に、宣言のポインターの一部です。 例:  
  
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
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 [C 拡張ストレージ クラス属性](../c-language/c-extended-storage-class-attributes.md)
