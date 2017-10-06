---
title: "void (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- void_cpp
dev_langs:
- C++
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
caps.latest.revision: 9
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
ms.openlocfilehash: dea06f16979fab9aa4494b172d6d95193a9f3727
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="void-c"></a>void (C++)
関数の戻り値の型として `void` キーワードを使用した場合は、関数が値を戻さないことを示します。 関数のパラメーター リストで void を使用した場合は、関数がパラメーターを受け取らないことを示します。 ポインターの宣言で void を使用した場合は、ポインターが "汎用" であることを示します。  
  
 ポインターの型が場合**void \* **、ポインターで宣言されていない任意の変数を指すことができます、 **const**または`volatile`キーワード。 void ポインターは別の型にキャストしない限り、逆参照できません。 void ポインターは他の型のデータ ポインターに変換できます。  
  
 void ポインターは、関数を指すことはできますが、C++ のクラス メンバーを指すことはできません。  
  
 void 型の変数を宣言することはできません。  
  
## <a name="example"></a>例  
  
```  
// void.cpp  
void vobject;   // C2182  
void *pv;   // okay  
int *pint; int i;  
int main() {  
   pv = &i;  
   // Cast optional in C required in C++  
   pint = (int *)pv;  
}   
```  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 [基本型](../cpp/fundamental-types-cpp.md)
