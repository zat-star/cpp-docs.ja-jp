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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f3ece905f03dc788580afde3e526041e933e3072
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2218"></a>コンパイラ エラー C2218
'__vectorcall' と '/arch:IA32' は同時に使用できません  
  
 `__vectorcall` の呼び出し規約は、SSE2 (Streaming SIMD Extensions 2) 以上が搭載された x86 および x64 プロセッサのネイティブ コードでのみサポートされます。 詳細については、次を参照してください。 [_ _vectorcall](../../cpp/vectorcall.md)します。  
  
 このエラーを修正するには、SSE2、AVX、または AVX2 をターゲットにするようにコンパイラ オプションを変更します。 詳細については、「[/arch (x86)](../../build/reference/arch-x86.md)」を参照してください。
