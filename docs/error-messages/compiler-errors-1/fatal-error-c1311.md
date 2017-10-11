---
title: "致命的なエラー C1311 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1311
dev_langs:
- C++
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9aeb63e041ddfe26a8fc47afc838f2f5c3ce35d6
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1311"></a>致命的なエラー C1311
COFF 形式は、'var' をアドレスの数バイトと共に静的に初期化できません。  
  
 型に 4 バイト未満の記憶域を持つ変数に、コンパイル時に値を持つことはできません、アドレスを静的に割り当てられたことはできません。  
  
 このエラーは、それ以外の場合は、コードで発生する可能性が有効な C++ です。  
  
 次の例では、C1311 を引き起こす可能性のある 1 つの条件を示します。  
  
```  
char c = (char)"Hello, world";   // C1311  
char *d = (char*)"Hello, world";   // OK  
```
