---
title: "コンパイラ エラー C2466 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2466
dev_langs:
- C++
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a41ea550abff9e48973452996cf5621e6bc4c42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2466"></a>コンパイラ エラー C2466
サイズが 0 の配列を割り当てることができません。  
  
 配列が割り当てられているか、サイズが 0 で宣言されています。 配列のサイズの定数式は、0 より大きい整数である必要があります。 添字が 0 の配列宣言はクラス、構造体、または共用体メンバーに対してのみ、Microsoft 拡張機能でのみ有効です。 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md))。  
  
 次の例では、C2466 が生成されます。  
  
```  
// C2466.cpp  
// compile with: /c  
int i[0];   // C2466  
int j[1];   // OK  
char *p;  
```