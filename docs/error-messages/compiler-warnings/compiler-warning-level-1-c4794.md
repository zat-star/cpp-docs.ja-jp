---
title: "コンパイラの警告 (レベル 1) C4794 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4794
dev_langs: C++
helpviewer_keywords: C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cd5c04107afefca59b84059330b6b0b891b974e9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4794"></a>コンパイラの警告 (レベル 1) C4794
スレッドのローカル ストレージ変数 'variable' のセグメントが 'section name' から '.tls$' に変更されました  
  
 tls 変数を .tls$ で始まっていないセクションに配置するために [#pragma data_seg](../../preprocessor/data-seg.md) を使用しました。  
  
 .tls$*x* セクションは、 [__declspec(thread)](../../cpp/thread.md) 変数が定義されているオブジェクト ファイルに存在します。 EXE または DLL の .tls セクションはこれらのセクションから生成されます。  
  
## <a name="example"></a>例  
 次の例では C4794 が生成されます。  
  
```  
// C4794.cpp  
// compile with: /W1 /c  
#pragma data_seg(".someseg")  
__declspec(thread) int i;   // C4794  
  
// OK  
#pragma data_seg(".tls$9")  
__declspec(thread) int j;  
```