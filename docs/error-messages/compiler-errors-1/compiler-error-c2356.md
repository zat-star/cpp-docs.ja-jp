---
title: "コンパイラ エラー C2356 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2356
dev_langs: C++
helpviewer_keywords: C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 99f29fb1e651c8182c8aa4dc037fc8cd6af6c6cc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2356"></a>コンパイラ エラー C2356
初期化セグメントは翻訳単位の間で変更する必要があります。  
  
 以下の原因が考えられます。  
  
-   `#pragma init_seg`セグメントの初期化コードに続く  
  
-   `#pragma init_seg`別の前に`#pragma init_seg`  
  
 を解決するのには、モジュールの先頭にセグメントの初期化コードを移動します。 複数の領域を初期化する必要がある場合、は、それらを個別のモジュールを移動します。  
  
 次の例では、C2356 が生成されます。  
  
```  
// C2356.cpp  
#pragma warning(disable : 4075)  
  
int __cdecl myexit(void (__cdecl *)());  
int __cdecl myexit2(void (__cdecl *)());  
  
#pragma init_seg(".mine$m",myexit)  
#pragma init_seg(".mine$m",myexit2)   // C2356  
```