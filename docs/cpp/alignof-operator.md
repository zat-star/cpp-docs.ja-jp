---
title: "__alignof 演算子 | Microsoft Docs"
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
  - "__alignof"
  - "alignof"
  - "alignas"
  - "__alignof_cpp"
  - "alignof_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__alignof キーワード [C++]"
  - "alignas"
  - "構造体の配置"
  - "alignof"
  - "型 [C++], 配置の要件"
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __alignof 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+11 では、指定した型の配置をバイト単位で返す `alignof` 演算子が導入されています。  移植性を最大にするため、Microsoft 固有の \_\_alignof 演算子ではなく、alignof 演算子を使用してください。  
  
 **Microsoft 固有の仕様 →**  
  
 型の配置要件である **size\_t** 型の値を返します。  
  
## 構文  
  
```  
  
        __alignof(   
   type    
)  
```  
  
## 解説  
 例:  
  
|式|値|  
|-------|-------|  
|**\_\_alignof\( char \)**|1|  
|**\_\_alignof\( short \)**|2|  
|**\_\_alignof\( int \)**|4|  
|**\_\_alignof\( \_\_int64 \)**|8|  
|**\_\_alignof\( float \)**|4|  
|**\_\_alignof\( double \)**|8|  
|**\_\_alignof\( char\* \)**|4|  
  
 `__alignof` 値は、基本型の `sizeof` 値と同じです。  ただし、次の例を検討します。  
  
```  
typedef struct { int a; double b; } S;  
// __alignof(S) == 8  
```  
  
 この場合、`__alignof` 値は、構造体内の最大要素の配置要件です。  
  
 同様に、  
  
```  
typedef __declspec(align(32)) struct { int a; } S;  
```  
  
 `__alignof(S)` と `32` が等価です。  
  
 `__alignof` の使用方法の 1 つは、独自のメモリ割り当てルーチンの 1 つへのパラメーターとしての使用です。  たとえば、次の定義済みの構造体 `S` を指定して、`aligned_malloc` という名前のメモリ割り当てルーチンを呼び出し、特定の配置境界にメモリを割り当てることができます。  
  
```  
typedef __declspec(align(32)) struct { int a; double b; } S;  
int n = 50; // array size  
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));  
```  
  
 配置の変更の詳細については、次を参照してください。  
  
-   [pack](../preprocessor/pack.md)  
  
-   [align](../cpp/align-cpp.md)  
  
-   [\_\_unaligned](../cpp/unaligned.md)  
  
-   [\/Zp \(構造体メンバーの配置\)](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md)  
  
-   [構造体の配置例](../build/examples-of-structure-alignment.md) \(x64 固有\)  
  
 x86 と x64 用のコード内の配置の違いの詳細については、  
  
-   「[x86 コンパイラとの競合](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)」を参照してください。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [単項演算子を含む式](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)