---
title: "再帰関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 38d98e568b88d8b26be2a04a9b643fb0d99a9712
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="recursive-functions"></a>再帰関数
C プログラムのどの関数も、再帰的に、つまり、その関数自体を呼び出すことができます。 再帰呼び出しの数は、スタックのサイズに制限されます。 スタック サイズを設定するリンカー オプションについては、[/STACK (スタック割り当て)](../build/reference/stack-stack-allocations.md)/(/STACK) リンカーオプションに関するページをご覧ください。 関数が呼び出されるたびに、以前の未完了の呼び出しの値が上書きされないように、新しいストレージがパラメーター、**auto** 変数、および **register** 変数に割り当てられます。 パラメーターは、作成元の関数のインスタンスにのみ直接アクセスできます。 前のパラメーターは、関数のその後のインスタンスに直接アクセスできません。  
  
 **"静的"** ストレージで宣言された変数は、再帰呼び出しごとに新しいストレージを必要としないことに注意してください。 このようなストレージは、プログラムの有効期間にわたって存続します。 このような変数への各参照は、同じストレージ領域にアクセスします。  
  
## <a name="example"></a>例  
 この例は、再帰呼び出しを示しています。  
  
```  
int factorial( int num );      /* Function prototype */  
  
int main()  
{  
    int result, number;  
    .  
    .  
    .  
    result = factorial( number );  
}  
  
int factorial( int num )      /* Function definition */  
{  
    .  
    .  
    .  
    if ( ( num > 0 ) || ( num <= 10 ) )  
        return( num * factorial( num - 1 ) );  
}  
  
```  
  
## <a name="see-also"></a>関連項目  
 [関数呼び出し](../c-language/function-calls.md)
