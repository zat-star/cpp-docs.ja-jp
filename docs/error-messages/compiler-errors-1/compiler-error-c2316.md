---
title: "コンパイラ エラー C2316 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2316
dev_langs:
- C++
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 60e5fb2346c92b3005e7cbfe1663d43cc0a12cdc
ms.contentlocale: ja-jp
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-error-c2316"></a>コンパイラ エラー C2316

> '*例外*': デストラクターまたはコピー コンス トラクターはアクセスできないためキャッチできません  
  
値または参照によって例外がキャッチされましたが、コピー コンストラクターや代入演算子にアクセスできませんでした。  
  
このコードは、バージョンの Visual Studio 2003 では、前に Visual C で受け取られたが、エラーになりました。  
  
Visual Studio 2015 で準拠の変更にこのエラーから派生した MFC 例外の不適切な catch ステートメントには適用が行われた`CException`です。 `CException`継承されたプライベート コピー コンス トラクターが、クラスとその派生クラスはコピー不可にし、値、つまりまた値によってためキャッチできませんで渡されることはできません。 以前、実行時にキャッチされない例外の原因の値で MFC の例外をキャッチするステートメントをキャッチできてもコンパイラ正しく識別するようにこのような状況とエラー C2316 を報告します。 この問題を修正するのにはなく、独自の例外ハンドラーの記述がコードの該当する場合、MFC の例外をキャッチ参照渡しで代わりに、MFC TRY/CATCH マクロを使用することをお勧めします。   
  
## <a name="example"></a>例  
 次の例では C2316 が生成されます。  
  
```  
// C2316.cpp  
// compile with: /EHsc  
#include <stdio.h>  
  
extern "C" int printf_s(const char*, ...);  
  
struct B   
{  
public:  
    B() {}  
    // Delete the following line to resolve.  
private:  
    // copy constructor  
    B(const B&)   
    {  
    }  
};  
  
void f(const B&)   
{  
}  
  
int main()   
{  
    try   
    {  
        B aB;  
        f(aB);  
    }  
    catch (B b) {   // C2316  
        printf_s("Caught an exception!\n");     
    }  
}  
```
