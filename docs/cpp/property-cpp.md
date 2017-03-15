---
title: "property (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "property_cpp"
  - "Property"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec キーワード [C++], プロパティ"
  - "property __declspec キーワード"
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# property (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 この属性は、クラスまたは構造体の定義の非静的 "仮想データ メンバー" に適用できます。  コンパイラは、参照を関数呼び出しに変更することにより、これらの "仮想データ メンバー" をデータ メンバーとして処理します。  
  
## 構文  
  
```  
  
      __declspec( property( get=get_func_name ) ) declarator  
__declspec( property( put=put_func_name ) ) declarator  
__declspec( property( get=get_func_name, put=put_func_name ) ) declarator  
```  
  
## 解説  
 コンパイラがメンバー選択演算子 \("**.**" または "**\-\>**"\) の右側でこの属性で宣言されたデータ メンバーを検出した場合、そのような式が左辺値または右辺値であるかどうかにより、**get** または **put** 関数に操作を変換します。  `+=` など、より複雑なコンテキストでは、**get** と **put** の両方を実行することによって書き換えが行われます。  
  
 この属性は、クラスまたは構造体の定義の空の配列の宣言でも使用できます。  次に例を示します。  
  
```  
__declspec(property(get=GetX, put=PutX)) int x[];  
```  
  
 前のステートメントは、`x[]` を 1 つ以上の配列インデックスで使用できることを示します。  この例では、`i=p->x[a][b]` は `i=p->GetX(a, b)` になります。また、`p->x[a][b] = i` は `p->PutX(a, b, i);` になります。  
  
 **END Microsoft 固有の仕様**  
  
## 使用例  
  
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
  
## 参照  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)