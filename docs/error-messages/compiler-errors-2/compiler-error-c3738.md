---
title: "コンパイラ エラー C3738 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3738
dev_langs: C++
helpviewer_keywords: C3738
ms.assetid: dd3ee011-e204-4264-bf3a-da32c4ef7038
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d8105ab081b939998d72d1bf470fe2b1e92addac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3738"></a>コンパイラ エラー C3738
'calling_convention': 明示的なインスタンス化の呼び出し規約には、インスタンス化されているテンプレートの一致する必要があります  
  
 明示的なインスタンス化で呼び出し規約を指定しないことをお勧めします。 、必要な場合は、呼び出し規約に一致する必要があります。  
  
## <a name="example"></a>例  
 次の例では、C3738 を生成します。  
  
```  
// C3738.cpp  
// compile with: /clr  
// processor: x86  
#include <stdio.h>  
template< class T >  
void f ( T arg ) {   // by default calling convention is __cdecl  
   printf ( "f: %s\n", __FUNCSIG__ );  
}  
  
template   
void __stdcall f< int > ( int arg );   // C3738  
// try the following line instead  
// void f< int > ( int arg );  
  
int main () {  
   f(1);  
   f< int > ( 1 );  
}  
```