---
title: "コンパイラ エラー C2218 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2218
dev_langs:
- C++
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3ca2e431fdfeff3c9dc957bee46f84cfd2c04162
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2218"></a>コンパイラ エラー C2218
'__vectorcall' と '/arch:IA32' は同時に使用できません  
  
 `__vectorcall` の呼び出し規約は、SSE2 (Streaming SIMD Extensions 2) 以上が搭載された x86 および x64 プロセッサのネイティブ コードでのみサポートされます。 詳細については、次を参照してください。 [_ _vectorcall](../../cpp/vectorcall.md)です。  
  
 このエラーを修正するには、SSE2、AVX、または AVX2 をターゲットにするようにコンパイラ オプションを変更します。 詳細については、「[/arch (x86)](../../build/reference/arch-x86.md)」を参照してください。
