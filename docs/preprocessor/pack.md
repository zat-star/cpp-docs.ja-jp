---
title: "pack | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pack_CPP"
  - "vc-pragma.pack"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "pack プラグマ"
  - "プラグマ, pack"
ms.assetid: e4209cbb-5437-4b53-b3fe-ac264501d404
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pack
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

構造体メンバー、共用体メンバー、およびクラス メンバーのパッキング アラインメントを指定します。  
  
## 構文  
  
```  
  
#pragma pack( [ show ] | [ push | pop ] [, identifier ] , n  )  
```  
  
## 解説  
 クラスをパッキングすると、そのメンバーはメモリ内で互いの直後に配置されます。そのため、一部またはすべてのメンバーがターゲット アーキテクチャの既定のアラインメントより小さい境界内にアラインされる場合があります。  `pack` では、データ宣言レベルで制御できます。  これは、モジュール レベルの制御のみを提供するコンパイラ オプション [\/Zp](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md) とは異なります。  `pack` は、プラグマが参照された後の最初の `struct`、`union`、または `class` 宣言で有効になります。  `pack` は、定義への影響はありません。  引数なしの `pack` を呼び出すと、`n` が **\/Zp** コンパイラ オプションに設定された値に設定されます。  コンパイラ オプションを設定しない場合、既定値は 8 になります。  
  
 構造体の配置を変更すると、メモリの領域はそれほど使用されていなくても、パフォーマンスが低下したり、アラインメントされていないアクセスについてハードウェアで生成された例外を受け取る場合があります。  この例外動作は、[SetErrorMode](http://msdn.microsoft.com/library/windows/desktop/ms680621) を使用して変更できます。  
  
 **show** \(省略可能\)  
 パッキング アラインメントの現在のバイト値を表示します。  値は警告メッセージによって表示されます。  
  
 **push** \(省略可能\)  
 現在のパッキング アラインメント値を内部コンパイラ スタックにプッシュし、現在のパッキング アラインメント値を `n` に設定します。  `n` が指定されていない場合、現在のパッキング アラインメントの値がプッシュされます。  
  
 **pop** \(省略可能\)  
 内部コンパイラ スタックの最上部からレコードを削除します。  `n` が **pop** で指定されていない場合、スタックの最上位の結果のレコードに関連付けられているパッキング値は、新しいパッキング アラインメント値になります。  `n` が指定されている場合、たとえば `#pragma pack(pop, 16)` では、`n` が新しいパッキング アラインメント値になります。  `identifier` \(たとえば `#pragma pack(pop, r1)`\) でポップすると、スタック内のすべてのレコードが `identifier` のあるレコードまでポップされます。  このレコードがポップされ、スタックの最上位の結果のレコードに関連付けられているパッキング値が新しいパッキング アラインメント値になります。  スタック内のどのレコードにもない `identifier` でポップすると、**pop** は無視されます。  
  
 `identifier` \(省略可能\)  
 **push** と共に使用した場合、内部コンパイラ スタックのレコードに名前を割り当てます。  **pop** と共に使用した場合、`identifier` が削除されるまでレコードを内部スタックからポップします。`identifier` が内部スタックにない場合は何もポップされません。  
  
 `n` \(省略可能\)  
 パッキングに使用される値 \(バイト単位\) を指定します。  コンパイラ オプション [\/Zp](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md) がモジュールに設定されていない場合、`n` の既定値は 8 になります。  有効値は 1、2、4、8、および 16 です。  メンバーのアラインメントは、`n` の倍数またはメンバーのサイズの倍数の小さい方の境界上にあります。  
  
 `#pragma pack(pop,` `identifier``,` `n``)` が未定義です。  
  
 アラインメントの変更方法の詳細については、次のトピックを参照してください。  
  
-   [\_\_alignof](../cpp/alignof-operator.md)  
  
-   [align](../cpp/align-cpp.md)  
  
-   [\_\_unaligned](../cpp/unaligned.md)  
  
-   [構造体の配置例](../build/examples-of-structure-alignment.md) \(x64 固有\)  
  
    > [!WARNING]
    >  Visual Studio 2015 以降では、標準の alignas および alignof 演算子を使用できることに注意してください。これらは `__alignof` および `declspec( align )` とは異なり、コンパイラ間で移植できます。  C\+\+ 標準はパッキングに対応していないため、ターゲット アーキテクチャのワード サイズより小さいアラインメントを指定するには、まだ `pack` \(または他のコンパイラでの対応する拡張機能\) を使用する必要があります。  
  
## 使用例  
 次のサンプルでは、`pack` プラグマを使用して、構造体のアラインメントを変更する方法を示します。  
  
```  
// pragma_directives_pack.cpp  
#include <stddef.h>  
#include <stdio.h>  
  
struct S {  
   int i;   // size 4  
   short j;   // size 2  
   double k;   // size 8  
};  
  
#pragma pack(2)  
struct T {  
   int i;  
   short j;  
   double k;  
};  
  
int main() {  
   printf("%zu ", offsetof(S, i));  
   printf("%zu ", offsetof(S, j));  
   printf("%zu\n", offsetof(S, k));  
  
   printf("%zu ", offsetof(T, i));  
   printf("%zu ", offsetof(T, j));  
   printf("%zu\n", offsetof(T, k));  
}  
```  
  
```  
0 4 8  
0 4 6  
```  
  
## 使用例  
 次の例は、**push** 構文、**pop** 構文、および **show** 構文の使用方法を示しています。  
  
```  
// pragma_directives_pack_2.cpp  
// compile with: /W1 /c  
#pragma pack()   // n defaults to 8; equivalent to /Zp8  
#pragma pack(show)   // C4810  
#pragma pack(4)   // n = 4  
#pragma pack(show)   // C4810  
#pragma pack(push, r1, 16)   // n = 16, pushed to stack  
#pragma pack(show)   // C4810  
#pragma pack(pop, r1, 2)   // n = 2 , stack popped  
#pragma pack(show)   // C4810  
```  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)