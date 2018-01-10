---
title: "コンパイラの警告 (レベル 3) C4290 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4290
dev_langs: C++
helpviewer_keywords: C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f70a278cb3e660e89e1aba067cab9c20aacf8f62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4290"></a>コンパイラの警告 (レベル 3) C4290
C++ の例外の指定に、関数を示すは無視されます。  
  
 関数は、Visual C を受け付けますが、実装していませんが、例外指定を使用して宣言されます。 コードでは、例外は、コンパイル時に無視される仕様が再コンパイルする必要があります、リンクを再利用後で例外の指定をサポートするバージョン。  
  
 詳細については、次を参照してください。[例外の仕様 (スロー)](../../cpp/exception-specifications-throw-cpp.md)です。  
  
 使用してこの警告を回避することができます、[警告](../../preprocessor/warning.md)プラグマ。  
  
```  
#pragma warning( disable : 4290 )  
```  
  
 次のコード サンプルには、C4290 が生成されます。  
  
```  
// C4290.cpp  
// compile with: /EHs /W3 /c  
void f1(void) throw(int) {}   // C4290  
  
// OK  
void f2(void) throw() {}  
void f3(void) throw(...) {}  
```