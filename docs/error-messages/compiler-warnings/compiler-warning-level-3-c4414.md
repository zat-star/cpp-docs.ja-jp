---
title: "コンパイラの警告 (レベル 3) C4414 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4414
dev_langs:
- C++
helpviewer_keywords:
- C4414
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76745a1cf505a685bcb9a6d2e74faf98bad77556
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4414"></a>コンパイラの警告 (レベル 3) C4414
'function': 関数へのジャンプを短いに近い値に変換  
  
 短いジャンプは、限られた範囲内のアドレスに命令から分岐 compact 命令を生成します。 命令には、ジャンプとターゲット アドレスなど、関数定義の間の距離を表す短いオフセットが含まれています。 リンク中に、関数に移動またはの対象になるリンク時の最適化機能により、関数、短いオフセットから到達可能な範囲外に移動するのに可能性があります。 コンパイラが近いまたはまでのいずれかに、jmp 命令が必要なジャンプに特殊なレコードを生成する必要があります。 コンパイラでは、変換が行われます。  
  
 たとえば、次のコードでは、C4414 が生成されます。  
  
```  
// C4414.cpp  
// compile with: /W3 /c  
// processor: x86  
int DoParityEven();  
int DoParityOdd();  
unsigned char global;  
int __declspec(naked) DoParityEither()  
{  
   __asm  
   {  
      test global,0  
      jpe SHORT DoParityEven  // C4414  
      jmp SHORT DoParityOdd   // C4414  
   }  
}  
```