---
title: 'メンバー アクセス演算子: です。 パラメーターと&gt;|Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- .
- ->
dev_langs:
- C++
helpviewer_keywords:
- member access, expressions
- operators [C++], member access
- dot operator (.)
- -> operator
- member access, operators
- postfix operators [C++]
- . operator
- member access
ms.assetid: f8fc3df9-d728-40c5-b384-276927f5f1b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2958291551d081b4284c6683d62f6dd5de06f70d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="member-access-operators--and--gt"></a>メンバー アクセス演算子: です。 パラメーターと&gt;
## <a name="syntax"></a>構文  
  
```  
postfix-expression . name  
postfix-expression -> name  
```  
  
## <a name="remarks"></a>コメント  
 メンバー アクセス演算子**です。** および**->** 構造体、共用体、およびクラスのメンバーを参照するために使用します。 メンバー アクセス式は、選択したメンバーの値と型を持ちます。  
  
 メンバー アクセス式には、次の 2 つの形式があります。  
  
1.  最初のフォームでは、*後置式*構造体、クラス、または共用体の型の値を表すと*名前*指定された構造体、共用体、またはクラスのメンバーに名前します。 操作の値は、の*名前*が左辺値の場合と*後置式*左辺値です。  
  
2.  2 番目の形式で*後置式*構造体、共用体、またはクラスへのポインターを表すと*名前*指定された構造体、共用体、またはクラスのメンバーに名前します。 値が*名前*左辺値です。 **->** 演算子には、ポインターが逆参照します。 そのため、式 * e ***->** `member`と **(\****e***)** です。`member` (場所*e*ポインターを表します) と同じ結果が生じる (する場合を除く演算子は、 **->** または**\*** はオーバー ロードされます)。  
  
## <a name="example"></a>例  
 次の例に、メンバー アクセス演算子の両方の形式を示します。  
  
```  
// expre_Selection_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Date {  
   Date(int i, int j, int k) : day(i), month(j), year(k){}  
   int month;  
   int day;  
   int year;  
};  
  
int main() {  
   Date mydate(1,1,1900);  
   mydate.month = 2;     
   cout  << mydate.month << "/" << mydate.day  
         << "/" << mydate.year << endl;  
  
   Date *mydate2 = new Date(1,1,2000);  
   mydate2->month = 2;  
   cout  << mydate2->month << "/" << mydate2->day  
         << "/" << mydate2->year << endl;  
   delete mydate2;  
}  
```  
  
```Output  
2/1/1900  
2/1/2000  
```  
  
## <a name="see-also"></a>関連項目  
 [後置式](../cpp/postfix-expressions.md)   
 [C++ 組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [クラスと構造体](../cpp/classes-and-structs-cpp.md)   
 [構造体と共用体のメンバー](../c-language/structure-and-union-members.md)