---
title: "コンパイラの警告 (レベル 2) C4412 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4412
dev_langs:
- C++
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
caps.latest.revision: 9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 92aa12514088d0fbffbe826a495d76b49ab311d1
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-2-c4412"></a>コンパイラの警告 (レベル 2) C4412
'function': 関数のシグネチャには、型 'type' が含まれています。C++ オブジェクトは、純粋なコードの間で渡す安全でないと混合またはネイティブです。  
  
 **/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 で使用されなくなりました。  
  
 ランタイム エラーが発生することが安全でない状況が検出されました: からの呼び出しになっている、 **/clr: 純粋な**dllimport と関数のシグネチャを使用してインポートされた関数をコンパイル単位には、安全でない型が含まれています。 メンバー関数を含むまたは安全でない型は安全でない型への間接参照、データ メンバーがある場合、型は安全ではありません。  
  
 これは、呼び出し規約が純粋とネイティブ コード間で既定値が異なるのため安全ではありません (またはネイティブおよびマネージの混合)。 インポートするときに (を介して`dllimport`) 関数を**/clr: 純粋な**コンパイル単位、署名の各型の宣言がコンパイル単位 (される暗黙の呼び出し規約の違いは特に注意が必要である) 関数をエクスポートすると同じことを確認します。  
  
 仮想メンバー関数は、傾向が予期しない結果が得られます。  ただし、正しい結果が得られるように、非仮想関数も含めてをテストしてください。 正しい結果が発生している場合は、この警告は無視できます。  
  
 詳細については**/clr: 純粋な**を参照してください[方法:/clr:pure に移行: 純粋な (C + +/CLI)](../../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)します。  
  
 C4412 が既定ではオフです。 参照してください[コンパイラの警告ことは既定で無効](../../preprocessor/compiler-warnings-that-are-off-by-default.md)と[dllexport、dllimport](../../cpp/dllexport-dllimport.md)の詳細。  
  
 この警告を解決するのには、型からのすべての機能を削除します。  
  
## <a name="example"></a>例  
 次の例では、C4412 を生成します。  
  
```  
// C4412.cpp  
// compile with: /c /W2 /clr:pure  
#pragma warning (default : 4412)  
  
struct Unsafe {  
   virtual void __cdecl Test();  
};  
  
struct Safe {  
   int i;  
};  
  
__declspec(dllimport) Unsafe * __cdecl func();  
__declspec(dllimport) Safe * __cdecl func2();  
  
int main() {  
   Unsafe *pUnsafe = func();   // C4412  
   // pUnsafe->Test();  
  
   Safe *pSafe = func2();   // OK  
}  
```  
  
## <a name="example"></a>例  
 次のサンプルは、2 つの型を宣言するヘッダー ファイルです。 `Unsafe`型のメンバー関数があるため安全ではありません。  
  
```  
// C4412.h  
struct Unsafe {  
   // will be __clrcall if #included in pure compilation  
   // defaults to __cdecl in native or mixed mode compilation  
   virtual void Test(int * pi);  
  
   // try the following line instead  
   // virtual void __cdecl Test(int * pi);  
};  
  
struct Safe {  
   int i;  
};  
```  
  
## <a name="example"></a>例  
 このサンプルでは、ヘッダー ファイルで定義された型と関数をエクスポートします。  
  
```  
// C4412_2.cpp  
// compile with: /LD  
#include "C4412.h"  
  
void Unsafe::Test(int * pi) {  
   *pi++;  
}  
  
__declspec(dllexport) Unsafe * __cdecl func() { return new Unsafe; }  
__declspec(dllexport) Safe * __cdecl func2() { return new Safe; }  
```  
  
## <a name="example"></a>例  
 既定呼び出し規約、 **/clr: 純粋な**コンパイルとは異なるネイティブ コンパイルします。  C4412.h が含まれている`Test`既定値は`__clrcall`です。 コンパイルして、このプログラムを実行する場合 (使用しない**/c**)、プログラムは例外をスローします。  
  
 次の例では、C4412 を生成します。  
  
```  
// C4412_3.cpp  
// compile with: /W2 /clr:pure /c /link C4412_2.lib  
#pragma warning (default : 4412)  
#include "C4412.h"  
  
__declspec(dllimport) Unsafe * __cdecl func();  
__declspec(dllimport) Safe * __cdecl func2();  
  
int main() {  
   int n = 7;  
   Unsafe *pUnsafe = func();   // C4412  
   pUnsafe->Test(&n);  
  
   Safe *pSafe = func2();   // OK  
}  
```
