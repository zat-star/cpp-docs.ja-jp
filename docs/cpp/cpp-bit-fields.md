---
title: "C++ ビット フィールド | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ビット フィールド"
  - "bitfield"
  - "フィールド [C++], ビット"
ms.assetid: 6f4b62e3-cc1d-4e5d-bf34-05904104f71a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ ビット フィールド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラスと構造体には、整数型よりも記憶領域の占有率が少ないメンバーを含めることができます。  これらのメンバーは、ビット フィールドとして指定されます。  bit\-field *member\-declarator* 指定の構文は次のとおりです。  
  
## 構文  
  
```  
  
declarator  : constant-expression  
```  
  
## コメント  
 `declarator` \(省略可能\) は、プログラム内でメンバーにアクセスするために使用される名前です。  整数型 \(列挙型を含む\) である必要があります。  *constant\-expression* は、構造体内でメンバーが占有するビット数を指定します。  匿名ビット フィールド \(つまり、識別子のないビット フィールド メンバー\) はパディング用に使用できます。  
  
> [!NOTE]
>  名前のない幅 0 のビット フィールドは、次のビット フィールドの割り当てが次の `type` 境界になるように強制します。`type` はメンバーの型です。  
  
 次の例では、ビット フィールドを持つ構造体を宣言します。  
  
```  
// bit_fields1.cpp  
// compile with: /LD  
struct Date {  
   unsigned short nWeekDay  : 3;    // 0..7   (3 bits)  
   unsigned short nMonthDay : 6;    // 0..31  (6 bits)  
   unsigned short nMonth    : 5;    // 0..12  (5 bits)  
   unsigned short nYear     : 8;    // 0..100 (8 bits)  
};  
```  
  
 `Date` 型のオブジェクトの概念的なメモリ レイアウトを次の図に示します。  
  
 ![データ オブジェクトのメモリ レイアウト](../cpp/media/vc38uq1.png "vc38UQ1")  
データ オブジェクトのメモリ レイアウト  
  
 `nYear` は 8 ビット長で、宣言されている **unsigned short** 型のワード境界をオーバーフローすることがあります。  したがって、新しい **unsigned short** の先頭で開始されます。  すべてのビット フィールドが基になる型の 1 つのオブジェクトに収まる必要はありません。宣言で要求されたビット数に従って、ストレージの新しい単位が割り当てられます。  
  
 **Microsoft 固有の仕様 →**  
  
 ビット フィールドとして宣言されたデータの順序は、上の図に示すように、下位から上位のビットへ向います。  
  
 **END Microsoft 固有の仕様**  
  
 構造体の宣言に、次の例のように、名前の付いていない長さが 0 のフィールドが含まれている場合、  
  
```  
// bit_fields2.cpp  
// compile with: /LD  
struct Date {  
   unsigned nWeekDay  : 3;    // 0..7   (3 bits)  
   unsigned nMonthDay : 6;    // 0..31  (6 bits)  
   unsigned           : 0;    // Force alignment to next boundary.  
   unsigned nMonth    : 5;    // 0..12  (5 bits)  
   unsigned nYear     : 8;    // 0..100 (8 bits)  
};  
```  
  
 メモリ レイアウトは次の図のようになります。  
  
 ![長さ 0 のビット フィールドを持つデータ オブジェクトのレイアウト](../Image/vc38UQ2.png "vc38UQ2")  
長さ 0 のビット フィールドを持つデータ オブジェクトのレイアウト  
  
 ビット フィールドの基になる型は「[Fundamental Types \(基本型\)](../cpp/fundamental-types-cpp.md)」で説明されているように、整数型である必要があります。  
  
## ビット フィールドの制約  
 次の一覧は、ビット フィールドの不適切な操作を詳述します。  
  
1.  ビット フィールドのアドレスの取得。  
  
2.  ビット フィールドでの参照の初期化。  
  
## 参照  
 [クラスと構造体](../Topic/Classes%20and%20Structs%20\(C++\).md)