---
title: "コンパイラの警告 (レベル 1) C4799 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4799
dev_langs:
- C++
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 617a6b2d009744adb0a53685976ee07266cf4490
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4799"></a>コンパイラの警告 (レベル 1) C4799
関数 'function' の最後に EMMS のないです。  
  
 関数が少なくとも&1; つの MMX 命令が EMMS 命令はありません。 マルチ メディアの命令を使用すると、EMMS 命令が使用することも MMX コードの最後に、マルチ メディア タグ ワードをオフにします。 EMMS の手順の詳細については、次を参照してください。[に EMMS の使用に関するガイドライン](http://msdn.microsoft.com/en-us/a0c3b1e4-01a4-419c-a58f-ff1e97dea7d3)します。  
  
 返す前に EMMS 命令を実行する ivec.h の使用、コードが正しく使用されないことと、C4799 が表示されます。 これは、これらのヘッダーの場合は false 警告です。 この操作は、ivec.h で _SILENCE_IVEC_C4799 の定義を無効に可能性があります。 ただし、これでも保持すること、コンパイラからこの型の正しい警告に注意してください。  
  
 関連情報については、次を参照してください。、 [Intel の MMX 命令セット](../../assembler/inline/intel-s-mmx-instruction-set.md)します。
