---
title: "_ _alignof 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- alignas_cpp
- __alignof_cpp
- alignof_cpp
dev_langs:
- C++
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
caps.latest.revision: 11
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
ms.openlocfilehash: 66ec7ff196a4f22aec043d8b76faf0189e05cd0f
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="alignof-operator"></a>__alignof 演算子
C++11 では、指定した型の配置をバイト単位で返す `alignof` 演算子が導入されています。 移植性を最大にするため、Microsoft 固有の __alignof 演算子ではなく、alignof 演算子を使用してください。  
  
 **Microsoft 固有の仕様**  
  
 型の値を返します**size_t**型のアラインメント要件はします。  
  
## <a name="syntax"></a>構文  
  
```  
  
      __alignof(   
   type    
)  
```  
  
## <a name="remarks"></a>コメント  
 例:  
  
|式|値|  
|----------------|-----------|  
|**_ _alignof (char)**|1|  
|**_ _alignof (短い形式)**|2|  
|**_ _alignof (int)**|4|  
|**_ _alignof ( \__int64)**|8|  
|**_ _alignof (float)**|4|  
|**_ _alignof (double)**|8|  
|**_ _alignof (char\* )**|4|  
  
 `__alignof` 値は、基本型の `sizeof` 値と同じです。 ただし、次の例を検討します。  
  
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
  
 `__alignof` の使用方法の 1 つは、独自のメモリ割り当てルーチンの 1 つへのパラメーターとしての使用です。 たとえば、次の定義済みの構造体 `S` を指定して、`aligned_malloc` という名前のメモリ割り当てルーチンを呼び出し、特定の配置境界にメモリを割り当てることができます。  
  
```  
typedef __declspec(align(32)) struct { int a; double b; } S;  
int n = 50; // array size  
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));  
```  
  
 配置の変更の詳細については、次を参照してください。  
  
-   [pack](../preprocessor/pack.md)  
  
-   [align](../cpp/align-cpp.md)  
  
-   [__unaligned](../cpp/unaligned.md)  
  
-   [/Zp (構造体メンバーの配置)](../build/reference/zp-struct-member-alignment.md)  
  
-   [構造体の配置例](../build/examples-of-structure-alignment.md)(x64 固有)  
  
 x86 と x64 用のコード内の配置の違いの詳細については、  
  
-   [x86 コンパイラとの競合](../build/conflicts-with-the-x86-compiler.md)  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [単項演算子を含む式](../cpp/expressions-with-unary-operators.md)   
 [キーワード](../cpp/keywords-cpp.md)
