---
title: void (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de70ec6758109bc765d0cec3552762288d51ded2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="void-c"></a>void (C++)
関数の戻り値の型として `void` キーワードを使用した場合は、関数が値を戻さないことを示します。 関数のパラメーター リストで void を使用した場合は、関数がパラメーターを受け取らないことを示します。 ポインターの宣言で void を使用した場合は、ポインターが "汎用" であることを示します。  
  
 ポインターの型が場合**void \*** 、ポインターで宣言されていない任意の変数を指すことができます、 **const**または`volatile`キーワード。 void ポインターは別の型にキャストしない限り、逆参照できません。 void ポインターは他の型のデータ ポインターに変換できます。  
  
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
 [基本的な型](../cpp/fundamental-types-cpp.md)