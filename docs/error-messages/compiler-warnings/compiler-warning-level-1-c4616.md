---
title: "コンパイラの警告 (レベル 1) C4616 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4616
dev_langs:
- C++
helpviewer_keywords:
- C4616
ms.assetid: 71e15265-c5bc-42ce-a6a9-4879892472b1
caps.latest.revision: 8
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
ms.openlocfilehash: 584a07701717afc40a738cf4088ec9cab2d98c0a
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4616"></a>コンパイラの警告 (レベル 1) C4616
\#プラグマの警告: 警告番号 'number' 有効なコンパイラ警告ではありません  
  
 指定した警告番号、[警告](../../preprocessor/warning.md)プラグマを再割り当てすることはできません。 このプラグマは無視されました。  
  
 次の例では、C4616 が生成されます。  
  
```  
// C4616.cpp  
// compile with: /W1 /c  
#pragma warning( disable : 0 )   // C4616  
#pragma warning( disable : 999 )   // OK  
#pragma warning( disable : 4998 )   // OK  
```
