---
title: "プロパティ (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- property_cpp
dev_langs:
- C++
helpviewer_keywords:
- property __declspec keyword
- __declspec keyword [C++], property
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
caps.latest.revision: 7
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
ms.openlocfilehash: d4cb68d02f9ee543c2d3271bc48ad4318352faa2
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="property-c"></a>property (C++)
**Microsoft 固有の仕様**  
  
 この属性は、クラスまたは構造体の定義の非静的 "仮想データ メンバー" に適用できます。 コンパイラは、参照を関数呼び出しに変更することにより、これらの "仮想データ メンバー" をデータ メンバーとして処理します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      __declspec( property( get=get_func_name ) ) declarator  
__declspec( property( put=put_func_name ) ) declarator  
__declspec( property( get=get_func_name, put=put_func_name ) ) declarator  
```  
  
## <a name="remarks"></a>コメント  
 コンパイラがメンバー選択演算子の右側にこの属性で宣言されたデータ メンバーを表示する場合 ("**.**「または」**->**") に変換する操作、 **の取得**または**put**関数は、このような式は、左辺値または右辺値かどうかによって異なります。 複雑なコンテキストなど"`+=`"、両方の手順を実行して書き換えが行わ**取得**と**put**です。  
  
 この属性は、クラスまたは構造体の定義の空の配列の宣言でも使用できます。 例:  
  
```  
__declspec(property(get=GetX, put=PutX)) int x[];  
```  
  
 前のステートメントは、`x[]` を 1 つ以上の配列インデックスで使用できることを示します。 この例では、`i=p->x[a][b]` は `i=p->GetX(a, b)` になります。また、`p->x[a][b] = i` は `p->PutX(a, b, i);` になります。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="example"></a>例  
  
```  
// declspec_property.cpp  
struct S {  
   int i;  
   void putprop(int j) {   
      i = j;  
   }  
  
   int getprop() {  
      return i;  
   }  
  
   __declspec(property(get = getprop, put = putprop)) int the_prop;  
};  
  
int main() {  
   S s;  
   s.the_prop = 5;  
   return s.the_prop;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [_ _declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)
