---
title: "const ポインターと volatile ポインター |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- volatile keyword [C++], and pointers
- pointers, and const
- pointers, and volatile
- const keyword [C++], volatile pointers
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ebf8d12c7c3b0f9578724fe772f24c0bc8c845ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="const-and-volatile-pointers"></a>const ポインターと volatile ポインター
[Const](../cpp/const-cpp.md)と[揮発性](../cpp/volatile-cpp.md)キーワードは、ポインターの処理方法を変更します。 **Const**キーワードは、初期化後に、ポインターを変更できないことを指定します。 ポインターはその後、変更から保護します。  
  
 `volatile` キーワードは、後に続く名前に関連付けられた値をユーザー アプリケーション以外の操作で変更できることを指定します。 したがって、`volatile` キーワードは、複数のプロセッサがアクセスできる共有メモリ内のオブジェクト、または、割り込みサービス ルーチンとの通信に使用するグローバル データ領域を宣言する場合に便利です。  
  
 名前が `volatile` として宣言されていると、プログラムによって名前がアクセスされるたびに、コンパイラはメモリから値を再度読み込みます。 これによって、可能な最適化が大幅に減少します。 ただし、オブジェクトの状態が予期せず変わる場合、これが予測可能なプログラムの実行を保証する唯一の方法になります。  
  
 としてのポインターによって指されるオブジェクトを宣言する**const**または`volatile`フォームの宣言を使用します。  
  
```  
const char *cpch;  
volatile char *vpch;  
```  
  
 ポインターの値を宣言する — ポインターに格納されている実際のアドレスは、— として**const**または`volatile`フォームの宣言を使用します。  
  
```  
char * const pchc;  
char * volatile pchv;  
```  
  
 C++ 言語のオブジェクトの変更を可能にする代入は回避またはとして宣言されたポインター **const**です。 このような代入を実行すると、オブジェクトまたはポインターを宣言したときの情報が削除されるため、元の宣言の意図に反することになります。 次に宣言の例を示します。  
  
```  
const char cch = 'A';  
char ch = 'B';  
```  
  
 2 つのオブジェクトの前の宣言がある (`cch`、型の**const char**、および`ch`、型の**char)**、次の宣言と初期化は無効です。  
  
```  
const char *pch1 = &cch;  
const char *const pch4 = &cch;  
const char *pch5 = &ch;  
char *pch6 = &ch;  
char *const pch7 = &ch;  
const char *const pch8 = &ch;  
```  
  
 次の宣言と初期化はエラーになります。  
  
```  
char *pch2 = &cch;   // Error  
char *const pch3 = &cch;   // Error  
```  
  
 `pch2` の宣言は、定数オブジェクトを変更する可能性があるポインターを宣言するため、許可されません。 `pch3` 宣言は、オブジェクトではなく `pointer` が定数であることを指定します。この宣言は、`pch2` 宣言が許可されないのと同じ理由で許可されません。  
  
 次の 8 つの代入は、ポインターを介した代入と、前に宣言したポインター値の変更を示しています。ここでは、初期化が `pch1` から `pch8` まで正しかったと仮定します。  
  
```  
*pch1 = 'A';  // Error: object declared const  
pch1 = &ch;   // OK: pointer not declared const  
*pch2 = 'A';  // OK: normal pointer  
pch2 = &ch;   // OK: normal pointer  
*pch3 = 'A';  // OK: object not declared const  
pch3 = &ch;   // Error: pointer declared const  
*pch4 = 'A';  // Error: object declared const  
pch4 = &ch;   // Error: pointer declared const  
```  
  
 として宣言されたポインター `volatile`、またはの組み合わせとして**const**と`volatile`、同じ規則に従います。  
  
 ポインター **const**オブジェクトは、次のように関数宣言で使用多くの場合。  
  
```  
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );  
```  
  
 前のステートメントは、関数を宣言[strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)へのポインター型の 3 つの引数の 2 つが、`char`です。 引数が参照によって渡されますないため、値によって関数は両方を変更するために解放`strDestination`と`strSource`場合`strSource`として宣言されていない**const**です。 宣言`strSource`として**const**により、呼び出し元`strSource`呼び出された関数では変更できません。  
  
> [!NOTE]
>  標準変換があるため*typename*  **\*** に**const** *typename*  **\***、型の引数を渡すことは**char \*** に[strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)です。 ただし、この逆は true になります。削除する暗黙的な変換が存在しない、 **const**オブジェクトまたはポインターからの属性です。  
  
 A **const**指定された型のポインターを同じ型のポインターに割り当てることができます。 ただし、ポインター外にある**const**に割り当てることはできません、 **const**ポインター。 次のコードは、正しい代入と正しくない代入を示します。  
  
```  
// const_pointer.cpp  
int *const cpObject = 0;  
int *pObject;  
  
int main() {  
pObject = cpObject;  
cpObject = pObject;   // C3892  
}  
```  
  
 次のサンプルは、オブジェクトへのポインターへのポインターがあるとき、オブジェクトを定数として宣言する方法を示します。  
  
```  
// const_pointer2.cpp  
struct X {  
   X(int i) : m_i(i) { }  
   int m_i;  
};  
  
int main() {  
   // correct  
   const X cx(10);  
   const X * pcx = &cx;  
   const X ** ppcx = &pcx;  
  
   // also correct  
   X const cx2(20);  
   X const * pcx2 = &cx2;  
   X const ** ppcx2 = &pcx2;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ポインター](../cpp/pointers-cpp.md)