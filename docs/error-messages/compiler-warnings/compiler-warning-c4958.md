---
title: "コンパイラの警告 C4958 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4958
dev_langs: C++
helpviewer_keywords: C4958
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4de819b0c18e141061f5d180f24558946bbf156b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4958"></a>コンパイラの警告 C4958
'operation': ポインター演算は検証可能ではありません  
  
 ポインター演算を使用すると、検証不能なイメージが作成されます。  
  
 詳細については、次を参照してください。[純粋なコードと検証可能なコード (C + + CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)です。  
  
 この警告は、エラーとして表示されます。無効にするには、 [warning](../../preprocessor/warning.md) プラグマ、または [/wd](../../build/reference/compiler-option-warning-level.md) コンパイラ オプションを使用します。  
  
 次の例では C4958 が生成されます。  
  
```  
// C4958.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4958 )  
using namespace System;  
  
int main( ) {  
   Int32 arr[] = new Int32[10];  
   Int32* p = &arr[0];  
   p++;   // C4958  
}  
```  
  
 コンパイラはポインター演算を使用して配列操作を実装します。 したがって、ネイティブ配列は検証不能になります。代わりに CLR 配列を使用してください。 詳細については、「 [配列](../../windows/arrays-cpp-component-extensions.md)」を参照してください。  
  
 次の例では C4958 が生成されます。  
  
```  
// C4958b.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4958 )  
  
int main() {  
   int array[5];  
   array[4] = 0;   // C4958  
}  
```