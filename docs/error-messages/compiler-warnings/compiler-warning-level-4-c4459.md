---
title: "コンパイラの警告 (レベル 4) C4459 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4459
dev_langs:
- C++
helpviewer_keywords:
- C4459
ms.assetid: ee9f6287-9c70-4b10-82a0-add82a13997f
caps.latest.revision: 0
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 87550474065639f6e1c7521ebfe76792d748ce9b
ms.contentlocale: ja-jp
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4459"></a>コンパイラの警告 (レベル 4) C4459
  
> 宣言 '*識別子*' グローバル宣言を非表示になります
  
宣言*識別子*ローカル スコープで、まったく同じ名前の宣言を非表示に*識別子*グローバル スコープでします。 この警告を参照するを認識できます。*識別子*このスコープで解決するにはローカルに宣言されたバージョンを、グローバル バージョンではなく、またはユーザーの意図ができない可能性があります。 一般に、優れたエンジニア リング手法としてグローバル変数の使用を最小限にするをお勧めします。 グローバル名前空間の汚染を最小限に抑えるするには、グローバル変数の名前付きの名前空間の使用をお勧めします。  
  
この警告は、Visual C コンパイラのバージョン 18.00 では、Visual Studio 2015 の新機能しました。 または、コードを移行するときに、後で、コンパイラのバージョンからの警告を抑制するのには、使用、 [/Wv:18](../../build/reference/compiler-option-warning-level.md)コンパイラ オプション。 

## <a name="example"></a>例
  
 次の例では、C4459 が生成されます。  
  
```cpp  
// C4459_hide.cpp
// compile with: cl /W4 /EHsc C4459_hide.cpp
int global_or_local = 1;

int main() { 
    int global_or_local; // warning C4459 
    global_or_local = 2;
} 
```  
  
この問題を解決する方法の 1 つが、グローバル変数の名前空間の作成が、使用しない、`using`に取り込むその名前空間スコープ、すべての参照を使用する必要があります、明確なのでディレクティブの修飾名。  
  
```cpp  
// C4459_namespace.cpp
// compile with: cl /W4 /EHsc C4459_namespace.cpp
namespace globals {
    int global_or_local = 1;
}

int main() { 
    int global_or_local; // OK 
    global_or_local = 2;
    globals::global_or_local = 3;
} 
```  

