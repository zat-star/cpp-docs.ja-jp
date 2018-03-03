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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 313123a75c2fbcf295d1c1d87aa423e76154091e
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2018
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
  
## <a name="see-also"></a>参照  
 [__declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)