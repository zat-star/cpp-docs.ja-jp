---
title: "コンパイラの警告 (レベル 4) C4463 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4463
dev_langs: C++
helpviewer_keywords: C4463
ms.assetid: a07ae70c-db4e-472b-8b58-9137d9997323
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 71b438de515a4fd01e7714de685ee0a89adb609e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4463"></a>コンパイラの警告 (レベル 4) C4463  
  
> オーバーフローです。割り当てる*値*のみからの値を保持できるビット フィールドに*low_value*に*high_value*  
  
割り当てられている*値*ビット フィールドを保持できる値の範囲外です。 符号付きビット フィールド型は、符号ビットの高位を使用できるよう *n* ビット フィールドのサイズ、範囲が符号付きビット フィールドは-2<sup>n-1</sup> 2<sup>n-1</sup>-1 で、中に符号なしビット フィールドが 0 ~ 2 の範囲にある<sup>n</sup>-1 です。  
  
## <a name="example"></a>例  
  
この例では生成しようとする型のビット フィールドに 3 の値を割り当てるため C4463`int`サイズが 2 を持つ-2 ~ 1 の範囲。  
  
この問題を解決するには、許容範囲に存在するものを割り当てられた値を変更できます。 宣言の型を変更するにはビット フィールドを 0 ~ 3 の範囲で符号なしの値を保持する場合は`unsigned`します。 フィールドを範囲-4 ~ 3 の値を保持する場合は 3 に、ビット フィールドのサイズを変更できます。  
  
```cpp  
// C4463_overflow.cpp
// compile with: cl /W4 /EHsc C4463_overflow.cpp
struct S { 
    int x : 2; // int type treats high-order bit as sign
}; 

int main() { 
    S s; 
    s.x = 3; // warning C4463: overflow; assigning 3 
    // to bit-field that can only hold values from -2 to 1 
    // To fix, change assigned value to fit in range,
    // increase size of bitfield, and/or change base type 
    // to unsigned.
} 
```  
