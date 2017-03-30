---
title: "コンパイラ エラー C2955 |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2955
dev_langs:
- C++
helpviewer_keywords:
- C2955
ms.assetid: 77709fb6-d69b-46fd-a62f-e8564563d01b
caps.latest.revision: 15
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
ms.sourcegitcommit: b790beb88de009e1c7161f3c9af6b3e21c22fd8e
ms.openlocfilehash: 1d2d589ad29896cda2657888c616388e50cc397a
ms.lasthandoff: 03/29/2017

---
# <a name="compiler-error-c2955"></a>コンパイラ エラー C2955
'identifier' : クラス テンプレートまたは別名ジェネリックを使用するには、テンプレートまたは汎用引数リストが必要です。  
  
 クラス テンプレートまたはクラス ジェネリックは、テンプレートまたは汎用引数リストを付けずに識別子として使用することはできません。  
  
 詳細については、次を参照してください。[クラス テンプレート](../../cpp/class-templates.md)です。  
  
 次の例では C2955 が生成され、その修正方法が示されています。  
  
```  
// C2955.cpp  
// compile with: /c  
template<class T>   
class X {};  
  
X x1;   // C2955  
X<int> x2;   // OK - this is how to fix it.  
```  
  
 C2955 は、クラス テンプレートで宣言される関数を行外で定義しようとした場合にも発生することがあります。  
  
```  
// C2955_b.cpp  
// compile with: /c  
template <class T>  
class CT {  
public:  
   void CTFunc();  
   void CTFunc2();  
};  
  
void CT::CTFunc() {}   // C2955  
  
// OK - this is how to fix it  
template <class T>  
void CT<T>::CTFunc2() {}  
  
```  
  
 C2955 は、ジェネリックを使用しているときも発生します。  
  
```  
// C2955_c.cpp  
// compile with: /clr  
generic <class T>   
ref struct GC {   
   T t;  
};  
  
int main() {  
   GC^ g;   // C2955  
   GC <int>^ g;  
}  
```

## <a name="example"></a>例
**2017 およびそれ以降の visual Studio:**コンパイラは、テンプレートがテンプレート パラメーター リストに (たとえばとして既定のテンプレート引数または非型テンプレート パラメーターの一部) が表示されたら正しくないテンプレート引数リストを診断します。 次のコードは、Visual Studio 2015 ではコンパイルされますが、Visual Studio 2017 ではエラーが発生します。

```
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias 
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

