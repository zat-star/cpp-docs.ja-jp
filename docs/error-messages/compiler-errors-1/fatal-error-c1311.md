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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a0d798ea53ebbbfe850b77b4b8176b35e2040ed8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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