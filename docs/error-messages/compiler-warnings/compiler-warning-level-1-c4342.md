---
title: "コンパイラの警告 (レベル 1) C4342 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4342
dev_langs: C++
helpviewer_keywords: C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: faea23fcfa1e323ec28d81aa5abeb27f3c87cef1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4342"></a>コンパイラの警告 (レベル 1) C4342
動作変更: '*関数*' 呼び出されると、メンバー演算子が以前のバージョンで呼び出されましたが、  
  
 バージョンの Visual Studio の 2002 の前に Visual C でメンバーが呼び出されましたが、この動作が変更され、コンパイラは、名前空間スコープで最適な一致を検索するようになりました。  
  
 メンバー演算子が見つかった場合、コンパイラは以前と見なしません任意の名前空間スコープ演算子。 名前空間スコープで優れた一致がある場合、現在のコンパイラ正しくは、以前のコンパイラが検討はありません。  
  
 現在のバージョンにコードを正常に移植する後に、この警告を無効にする必要があります。  コンパイラは偽陽性、コードに対してこの警告を生成する動作の変更が存在しません。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。  
  
 次の例では、C4342 が生成されます。  
  
```cpp  
// C4342.cpp  
// compile with: /EHsc /W1  
#include <fstream>  
#pragma warning(default: 4342)  
using namespace std;  
struct X : public ofstream {  
   X();  
};  
  
X::X() {  
   open( "ofs_bug_ev.txt." );  
   if ( is_open() ) {  
      *this << "Text" << "<-should be text" << endl;   // C4342  
      *this << ' ' << "<-should be space symbol" << endl;   // C4342  
   }  
}  
  
int main() {  
   X b;  
   b << "Text" << "<-should be text" << endl;  
   b << ' ' << "<-should be space symbol" << endl;  
}  
```