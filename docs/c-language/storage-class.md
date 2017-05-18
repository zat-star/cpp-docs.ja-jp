---
title: "ストレージ クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- linkage [C++], external
- function storage class
- function specifiers, storage class
- storage classes
- Microsoft-specific storage classes
- external linkage, storage-class specifiers
- static storage class specifiers
ms.assetid: 39a79ba6-edf5-42b6-8e45-f94227603dd6
caps.latest.revision: 8
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d2a6e5026e71d993675fff3674af3fe6d2f9be96
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="storage-class"></a>ストレージ クラス
関数定義では、ストレージ クラス指定子により、関数に `extern` または **static** のストレージ クラスが指定されます。  
  
## <a name="syntax"></a>構文  
 *function-definition*:  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq* は Microsoft 固有の仕様 */  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *storage-class-specifier*: /\* 関数定義用 \*/  
 **extern**  
  
 **static**  
  
 関数定義に*ストレージ クラス指定子*が含まれていない場合、ストレージ クラスは既定で `extern` になります。 関数を `extern` として明示的に宣言することもできますが、必須ではありません。  
  
 関数の宣言に*ストレージ クラス指定子* `extern` が含まれる場合、その識別子は、ファイル スコープで宣言されたあらゆる可視の該当識別子と同じリンケージを持ちます。 ファイル スコープで可視の宣言がない場合、その識別子は外部リンケージを持ちます。 識別子がファイル スコープで、*ストレージ クラス指定子*がない場合、その識別子は外部リンケージを持ちます。 外部リンケージは、その識別子の各インスタンスが同じオブジェクトまたは関数を表すことを意味します。 リンケージとファイル スコープの詳細については、「[有効期間、スコープ、可視性、およびリンケージ](../c-language/lifetime-scope-visibility-and-linkage.md)」を参照してください。  
  
 `extern` 以外のストレージ クラス指定子を持つブロック スコープの関数を宣言すると、エラーが発生します。  
  
 **static** ストレージ クラスとして宣言された関数は、定義されているソース ファイル内でのみ可視になります。 それ以外のすべての関数は、`extern` ストレージ クラスの指定が明示的か暗黙的かに関係なく、プログラムのすべてのソース ファイルで可視になります。 **static** ストレージ クラスを指定する必要がある場合は、その関数の宣言が最初に発生する場所 (存在する場合) の関数定義で宣言する必要があります。  
  
 **Microsoft 固有の仕様**  
  
 Microsoft 拡張機能が有効な場合、最初にストレージ クラスを指定せずに (または `extern` ストレージ クラスで) 宣言された関数が **static** ストレージ クラスとなるのは、最初と同じソース ファイルに含まれる関数定義で、**static** ストレージ クラスが明示的に指定された場合です。  
  
 /Ze コンパイラ オプションを使用してコンパイルすると、`extern` キーワードを使用してブロック内で宣言された関数はグローバルで可視になります。 /Za でコンパイルした場合は、これに該当しません。 ソース コードの移植性を考慮している場合は、この機能に依存しないでください。  
  
 **END Microsoft 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [C 関数の定義](../c-language/c-function-definitions.md)
