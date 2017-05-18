---
title: "コンパイラの警告 (レベル 1) C4615 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4615
dev_langs:
- C++
helpviewer_keywords:
- C4615
ms.assetid: 7b107c01-0da2-4e01-8b40-93813e30b94c
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 41ddf5e421e5840fa5d17dfb6a619a0d4ee1099d
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4615"></a>コンパイラの警告 (レベル 1) C4615
\#プラグマの警告: 不明なユーザーの警告の種類  
  
 無効な警告指定子が使用されていた**プラグマ**[警告](../../preprocessor/warning.md)します。 エラーを解決するには、有効な警告指定子を使用します。  
  
 次の例では、C4615 が生成されます。  
  
```  
// C4615.cpp  
// compile with: /W1 /LD  
#pragma warning(enable : 4401)   // C4615, 'enable' not valid specifier  
  
// use the code below to resolve the error  
// #pragma warning(default : 4401)  
```
