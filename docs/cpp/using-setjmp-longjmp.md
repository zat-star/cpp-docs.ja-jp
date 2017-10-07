---
title: "Setjmp longjmp の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- longjmp_cpp
- setjmp_cpp
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- SETJMPEX.H
- longjmp function in C++ programs
- SETJMP.H
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 356924c0a93f6d9d21bb417f84836385491b2144
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="using-setjmplongjmp"></a>setjmp/longjmp の使用
ときに[setjmp](../c-runtime-library/reference/setjmp.md)と[longjmp](../c-runtime-library/reference/longjmp.md)は一緒に使用すると、ローカル以外の実行方法を提供`goto`です。 これらは通常、標準呼び出し規約や復帰規約を使用せずに、前に呼び出されたルーチンのエラー処理または回復コードに実行の制御を渡すために使用されます。  
  
> [!CAUTION]
>  ただし、`setjmp` と `longjmp` は C++ オブジェクトのセマンティクスをサポートせず、ローカル変数の最適化を妨げることによってパフォーマンスを低下させる可能性があるため、C++ プログラムでは使用しないことをお勧めします。 使用することをお勧め`try` / `catch`代わりに構築します。  
  
 利用を決めた場合`setjmp` / `longjmp` C++ プログラムでは、含める SETJMP こともできます。H または SETJMPEX します。関数と C++ 例外処理の間の相互作用が正しく H します。 使用する場合[/EH](../build/reference/eh-exception-handling-model.md)をコンパイルするローカル オブジェクトのデストラクターがスタック アンワインド中に呼び出されます。 使用する場合**/EHs**コンパイル、および、関数呼び出しを使用する関数の 1 つに[nothrow](../cpp/nothrow-cpp.md)と関数を使用する`nothrow`呼び出し`longjmp`、デストラクター アンワインドが発生しない場合、オプティマイザーに依存します。  
  
 移植性のあるコードで、`goto` を呼び出す非ローカルの `longjmp` が実行される場合、フレーム ベースのオブジェクトの適切な破棄が行われない可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [C (構造化) と C++ の混合例外](../cpp/mixing-c-structured-and-cpp-exceptions.md)
