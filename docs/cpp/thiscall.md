---
title: _ _thiscall |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __thiscall
- __thiscall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9dccd9e80a23b1636bd869d406824c9997f4cdef
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="thiscall"></a>__thiscall
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 `__thiscall` 呼び出し規約はメンバー関数で使用され、可変個引数を使用しない C++ メンバー関数によって使用される既定の呼び出し規約です。 `__thiscall` では呼び出し先がスタックをクリーンアップしますが、これは `vararg` 関数では不可能です。 引数は、x86 アーキテクチャでは、スタックではなくレジスタ ECX を介して渡される `this` ポインターでスタックに右から左へプッシュされます。  
  
 `__thiscall` を使用する理由の 1 つは、メンバー関数が `__clrcall` を既定で使用するクラスにあります。 その場合、`__thiscall` を使用して、個々のメンバー関数をネイティブ コードから呼び出すことができます。  
  
 コンパイルするときに[/clr: 純粋な](../build/reference/clr-common-language-runtime-compilation.md)、すべての関数および関数ポインターは`__clrcall`指定しない限り、します。 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で非推奨とされています。  
  
 Visual C++ 2005 以前のリリースでは、`thiscall` がキーワードではないため、thiscall 呼び出し規約を明示的に指定できませんでした。  
  
 `vararg` メンバー関数は `__cdecl` の呼び出し規約を使用します。 関数のすべての引数は、スタックにプッシュされ、`this` ポインターが最後にスタックに配置されます。  
  
 この呼び出し規則は C++ だけに適用されるため、C の名前の装飾スキームはありません。  
  
 ARM 上および[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]マシン`__thiscall`が受け入れられたり、コンパイラによって無視されます。  
  
 静的でないクラス関数がアウトオブラインで宣言されている場合、アウトオブラインの宣言で呼び出し規則の修飾子を指定する必要はありません。 つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規則が定義の時点で仮定されます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)