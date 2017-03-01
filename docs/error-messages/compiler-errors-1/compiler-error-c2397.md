---
title: "コンパイラ エラー C2397 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2397
dev_langs:
- C++
ms.assetid: b418cf5a-d50d-4a6c-98a7-994ae35046d1
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 31f2b548fd13bc7702d44ef4a6d5dc5c34a5eb3c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2397"></a>コンパイラ エラー C2397
'type_1' から 'type_2' への変換が縮小変換が必要です。  
  
 均一な初期化を使用する場合、暗黙的な縮小変換が見つかりました。  
  
 割り当てと初期化で暗黙的な縮小変換では、C 言語および C++ ダイヤの多くのコード エラーの原因は、予期しないを絞り込む場合でもです。 コードをより安全なさせるには、標準の C++ では、初期化リストで縮小変換が発生したときに、診断メッセージが必要です。 Visual c では、診断は、Visual Studio 2015 で均一な初期化のサポートされている構文の先頭を使用する場合に、コンパイラ エラー C2397 です。 コンパイラ生成[コンパイラの警告 (レベル 1) C4838](../../error-messages/compiler-warnings/compiler-warning-level-1-c4838.md)リストまたは Visual Studio 2013 でサポートされている集約の初期化の構文を使用する場合。  
  
 縮小変換は変換された値の有効範囲は、ターゲットに適合することがわかっている場合でも問題ないことができます。 この場合は、知っている、コンパイラがより。 縮小変換を意図的に作成する場合、開発者の意図を明示的に静的キャストを使用します。 それ以外の場合、このエラー メッセージほとんどの場合を示して、バグ、コードで。 初期化するオブジェクトの入力を処理するのに十分な大きさである型であることを確認することで解決することができます。  
  
 次の例では、C2397 を生成し、その修正方法を示しています。  
  
```  
// C2397.cpp -- C++ narrowing conversion diagnostics  
// Compile by using: cl /EHsc C2397.cpp  
#include <vector>   
  
struct S1 {  
    int m1;  
    double m2, m3;  
};  
  
void function_C2397(double d1) {  
    char c1 { 127 };          // OK  
    char c2 { 513 };          // error C2397  
  
    std::vector<S1> vS1;  
    vS1.push_back({ d1, 2, 3 }); // error C2397  
  
    // Possible fix if you know d1 always fits in an int  
    vS1.push_back({ static_cast<int>(d1), 2, 3 });   
}  
```
