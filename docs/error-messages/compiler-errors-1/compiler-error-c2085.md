---
title: "コンパイラ エラー C2085 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2085
dev_langs: C++
helpviewer_keywords: C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 45805bbea2eca77ae81922088471e99de26be1e4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2085"></a>コンパイラ エラー C2085
'identifier': 仮パラメーター リストではなく  
  
 識別子は、仮パラメーター リストではなく、関数定義で宣言されました。 (ANSI C のみ)  
  
 次の例では、C2085 が生成されます。  
  
```  
// C2085.c  
void func1( void )  
int main( void ) {}   // C2085  
```  
  
 考えられる解決策:  
  
```  
// C2085b.c  
void func1( void );  
int main( void ) {}  
```  
  
 セミコロンの欠落している`func1()`のでは関数定義では、プロトタイプではないようになります`main`内で定義された`func1()`、識別子のエラー C2085 を生成する`main`です。