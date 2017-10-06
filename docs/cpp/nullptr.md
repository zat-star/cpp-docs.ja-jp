---
title: "nullptr |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- nullptr_cpp
dev_langs:
- C++
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 16bbbc38c61b2b6ff0539b2c71a0457b38465acb
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="nullptr"></a>nullptr
任意の生ポインター型に変換可能な `std::nullptr_t` 型の null ポインター定数を指定します。  ヘッダーを含めずに `nullptr` キーワードを使用できますが、コードで `std::nullptr_t` 型を使用する場合、`<cstddef>` ヘッダーを含めることにより定義を行う必要があります。  
  
> [!NOTE]
>  また `nullptr` キーワードは、マネージ コード アプリケーション用に C++/CLI でも定義されており、ISO 標準の C++ キーワードに対して互換性がありません。 使用して、コードをコンパイルする場合がある場合、 [/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションは、マネージ コードをターゲットを使用して`__nullptr`のすべての行のコードをコンパイラがネイティブな C++ 解釈を使用することを保証する必要があります。 詳細については、次を参照してください。 [nullptr](../windows/nullptr-cpp-component-extensions.md)です。  
  
## <a name="remarks"></a>コメント  
 null ポインター定数として `NULL` またはゼロ (`0`) を使用しないでください。`nullptr` は悪用に対する脆弱性が少なく、大半の状況でより適切に動作します。  たとえば、`func(std::pair<const char *, double>)` が指定されている場合に、`func(std::make_pair(NULL, 3.14))` を呼び出すとコンパイラ エラーが発生します。  NULL マクロは `0` に展開します。したがって、`std::make_pair(0, 3.14)` の呼び出しでは、func() の `std::pair<int, double>` パラメーター型に変換可能ではない `std::pair<const char *, double>` が返されます。  `func(std::make_pair(nullptr, 3.14))` は `std::make_pair(nullptr, 3.14)` に変換可能な `std::pair<std::nullptr_t, double>` を返すので、`std::pair<const char *, double>` の呼び出しは正常にコンパイルされます。  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)
