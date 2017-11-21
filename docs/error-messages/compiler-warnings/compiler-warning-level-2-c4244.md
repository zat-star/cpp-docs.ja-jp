---
title: "コンパイラの警告 (レベル 2) C4244 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4244
dev_langs: C++
helpviewer_keywords: C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7f2059d6b17d803740f70e0d640e212d15858705
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4244"></a>コンパイラの警告 (レベル 2) C4244
'argument': 'type1' から 'type2' にデータ損失の可能性への変換  
  
 A は整数型に変換された浮動小数点型です。  データが失われた可能性があります。  
  
 C4244 の場合は、互換性のある型を使用するようにプログラムを変更するか、別のロジックをコードに追加して、変換される値の範囲が使用している型と常に互換性があるようにします。  
  
 また c4244 レベル 3 および 4 です。参照してください[コンパイラの警告 (レベル 3 および 4) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では C4244 が生成されます。  
  
```  
// C4244_level2.cpp  
// compile with: /W2  
  
int f(int x){ return 0; }  
int main() {  
   double x = 10.1;  
   int i = 10;  
   return (f(x));   // C4244  
   // try the following line instead  
   // return (f(i));  
}  
```