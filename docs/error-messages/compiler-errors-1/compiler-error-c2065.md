---
title: "コンパイラ エラー C2065 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2065
dev_langs:
- C++
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
caps.latest.revision: 20
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 81686df4727ab2b3d5af749174a42016e8443e70
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2065"></a>コンパイラ エラー C2065
'identifier' : 定義されていない識別子です。  
  
 変数の型は、変数が使われる前に宣言されている必要があります。 また、関数が使うパラメーターは、関数が呼び出される前に宣言またはプロトタイプで宣言されている必要があります。  
  
 以下の原因が考えられます。  
  
1.  識別子名のスペルが間違っています。  
  
2.  識別子の大文字と小文字が間違っています。  
  
3.  文字列定数の後ろの閉じる引用符がありません。  
  
4.  C++ 標準ライブラリの反復子変数を宣言する C ランタイムのデバッグ バージョンでコンパイルする、`for`ループのスコープ外の反復子変数を使用しようと、`for`ループします。 C ランタイムのデバッグ バージョンと C++ 標準ライブラリのコードをコンパイルすることを意味[/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)します。  参照してください[反復子のデバッグ サポート](../../standard-library/debug-iterator-support.md)の詳細。  
  
5.  ビルド環境で現在サポートされていない SDK ヘッダー ファイルの関数を呼び出している可能性があります。  
  
6.  必要なインクルード ファイルを省略しています (特に、`VC_EXTRALEAN`、`WIN32_LEAN_AND_MEAN`、または `WIN32_EXTRA_LEAN` を定義している場合)。 これらのシンボルは、コンパイルの速度を上げるために、一部のヘッダー ファイルを windows.h と afxv_w32.h から除外します  (windows.h および afxv_w32.h で、除外された項目の最新の説明を確認してください)。  
  
7.  名前空間スコープが適切ではありません。 たとえば、完全修飾されていない C++ の標準ライブラリの関数と演算子を解決するには、`using` ディレクティブで名前空間 `std` を指定する必要があります。 次の例では、`using` ディレクティブがコメント アウトされ、`cout` が名前空間 `std` で定義されているため、コンパイルが失敗します。  
  
## <a name="example"></a>例  
 次の例では、C2065 を生成し、その修正方法を示しています。  
  
```  
// C2065.cpp  
// compile with: /EHsc  
// using namespace std;   // Uncomment this line to fix  
#include <iostream>  
int main() {  
   cout << "Hello" << endl;   // C2065  
  
   // Or try the following line instead  
   std::cout << "Hello" << std::endl;  
}  
```  
  
## <a name="example"></a>例  
 ジェネリック関数を呼び出すときに、目的の型の引数を使用しているパラメーターから推測できない場合は、コンパイラがエラーを報告します。 詳細については、次を参照してください。[ジェネリック関数 (C + +/CLI)](../../windows/generic-functions-cpp-cli.md)します。  
  
 次の例では、C2065 を生成し、その修正方法を示しています。  
  
```  
// C2065_b.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
int main() {  
   // global generic function call  
   G<T>(10);   // C2065  
   G<int>(10);   // OK - fix with a specific type argument  
}  
```  
  
## <a name="example"></a>例  
 このエラーは、Visual C++ 属性のパラメーター チェックを行う Visual C++ 2005 で行ったコンパイラ準拠作業の結果として生成されることもあります。  
  
 次の例では、C2065 を生成し、その修正方法を示しています。  
  
```  
// C2065_c.cpp  
// compile with: /c  
[module(DLL, name=MyLibrary)];   // C2065  
// try the following line instead  
// [module(dll, name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```
