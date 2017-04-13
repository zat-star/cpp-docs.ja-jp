---
title: "コンパイラ エラー C2099 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2099
dev_langs:
- C++
helpviewer_keywords:
- C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 74fdc75470600c29029c52e38ab2073e484dbde6
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2099"></a>コンパイラ エラー C2099
初期化子が定数ではありません。  
  
 このエラーは C コンパイラでのみ発生し、非自動変数に対してのみ発生します。  コンパイラは、プログラムの開始時に非自動変数を初期化します。変数の初期化に使用される値は定数でなければなりません。  
  
## <a name="example"></a>例  
 次の例では C2099 エラーが生成されます。  
  
```  
// C2099.c  
int j;  
int *p;  
j = *p;   // C2099 *p is not a constant  
```  
  
## <a name="example"></a>例  
 C2099 エラーは、コンパイラが下にある式に定数の圧縮を実行できないためにも発生することができます**/fp: 厳密な**ため、浮動小数点の有効桁数の環境設定 (を参照してください[_controlfp_s](../../c-runtime-library/reference/controlfp-s.md)詳細については) 実行時とコンパイル時に異なる場合があります。  
  
 定数の圧縮が失敗すると、コンパイラは C で使用できない動的な初期化を呼び出します。  
  
 このエラーを解決するには、モジュールを .cpp ファイルとしてコンパイルするか、式を簡単にします。  
  
 詳細については、「[/fp (浮動小数点の動作の指定)](../../build/reference/fp-specify-floating-point-behavior.md)」を参照してください。  
  
 次の例では C2099 エラーが生成されます。  
  
```  
// C2099_2.c  
// compile with: /fp:strict /c  
float X = 2.0 - 1.0;   // C2099  
float X2 = 1.0;   // OK  
```
