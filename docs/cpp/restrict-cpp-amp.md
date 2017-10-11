---
title: "制限 (C++ AMP) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- cpu_CPP
- amp_CPP
dev_langs:
- C++
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 13c07d1bb085663abe9492d92835b9e05b89c742
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)
制限指定子は、関数宣言およびラムダ宣言に適用できます。 制限は、関数のコードに適用され、また、C++ Accelerated Massive Parallelism (C++ AMP) ランタイムを使用するアプリケーションの関数の動作に適用されます。  
  
> [!NOTE]
>  については、`restrict`の一部であるキーワード、`__declspec`ストレージ クラス属性を参照してください[制限](../cpp/restrict.md)です。  
  
 `restrict` 句は次の形式をとります。  
  
|句|説明|  
|------------|-----------------|  
|`restrict(cpu)`|関数は C++ 言語をフルに使用できます。 restrict (cpu) 関数を使用して宣言された他の関数だけがこの関数を呼び出すことができます。|  
|`restrict(amp)`|関数は C++ AMP で高速化できる C++ 言語のサブセットのみを使用できます。|  
|連続した `restrict(cpu)` と `restrict(amp)`|関数は `restrict(cpu)` と `restrict(amp)` の両方の制約に従う必要があります。 関数は `restrict(cpu)`、`restrict(amp)`、`restrict(cpu, amp)`、または `restrict(amp, cpu)` を使用して宣言した関数から呼び出すことができます。<br /><br /> `restrict(A) restrict(B)` という形式は `restrict(A,B)` と書くことができます。|  
  
## <a name="remarks"></a>コメント  
 `restrict` キーワードは、コンテキスト キーワードです。 制限指定子の `cpu` と `amp` は予約語ではありません。 指定子の数を増やすことはできません。 `restrict` 句がない関数は `restrict(cpu)` 句を持つ関数と同じです。  
  
 `restrict(amp)` 句を持つ関数には次の制限があります。  
  
-   関数は `restrict(amp)` 句を持つ関数のみを呼び出すことができます。  
  
-   関数はインライン化できる必要があります。  
  
-   関数は、型が `int`、`unsigned int`、`float`、`double` の変数と、これらの型だけを含むクラスと構造体のみを宣言できます。 `bool` も宣言できますが、複合型で使用する場合は、4 バイト境界で配置する必要があります。  
  
-   ラムダ関数は、参照によってキャプチャできず、また、ポインターをキャプチャできません。  
  
-   参照と単一間接ポインターは、ローカル変数、関数の引数、戻り値の型としてのみサポートされています。  
  
-   以下は使用できません。  
  
    -   再帰  
  
    -   宣言された変数、[揮発性](../cpp/volatile-cpp.md)キーワード。  
  
    -   仮想関数  
  
    -   関数へのポインター  
  
    -   メンバー関数へのポインター  
  
    -   構造体へのポインター  
  
    -   ポインターへのポインター  
  
    -   `goto` ステートメント  
  
    -   ラベル付きステートメント  
  
    -   `try`、`catch`、`throw` ステートメント  
  
    -   グローバル変数  
  
    -   静的変数 使用して[tile_static キーワード](../cpp/tile-static-keyword.md)代わりにします。  
  
    -   `dynamic_cast` キャスト  
  
    -   `typeid` 演算子。  
  
    -   asm 宣言  
  
    -   可変個引数  
  
 関数制限の詳細については、次を参照してください。 [restrict (amp) 制限](http://go.microsoft.com/fwlink/p/?LinkId=251089)です。  
  
## <a name="example"></a>例  
 次の例を使用する方法を示しています、`restrict(amp)`句。  
  
```  
  
void functionAmp() restrict(amp) {}   
void functionNonAmp() {}   
  
void callFunctions() restrict(amp)   
{   
    // int is allowed.  
    int x;  
    // long long int is not allowed in an amp-restricted function. This generates a compiler error.  
    // long long int y;   
  
    // Calling an amp-restricted function is allowed.  
    functionAmp();   
  
    // Calling a non-amp-restricted function is not allowed.  
    // functionNonAmp();   
  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)
