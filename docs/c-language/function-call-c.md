---
title: "関数呼び出し (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0faf339877b075a1337c73ec5ca3c41a869ceec2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="function-call-c"></a>関数呼び出し (C)
"関数呼び出し" は、呼び出される関数の名前または関数ポインターの値、および、関数に渡される省略可能な引数の値を含む式です。  
  
## <a name="syntax"></a>構文  
 *postfix-expression*:  
 *postfix-expression*  **(**  *argument-expression-list* opt**)**  
  
 *argument-expression-list*:  
 *assignment-expression*  
  
 *argument-expression-list*  **,**  *assignment-expression*  
  
 *postfix-expression* は、関数アドレス (たとえば、関数の識別子または関数ポインターの値) に評価される必要があります。*argument-expression-list* は、式の (コンマ区切りの) リストで、各式の値 ("引数") が関数に渡されます。 *argument-expression-list* 引数は空の場合もあります。  
  
 関数呼び出しの式は、関数の戻り値の値と型を持ちます。 関数は配列型のオブジェクトを返すことができません。 関数の戻り値の型が `void` (つまり、値を返さない関数であると宣言されている) の場合、関数呼び出し式も `void` 型になります  (詳細については、「[関数呼び出し](../c-language/function-calls.md)」を参照してください)。  
  
## <a name="see-also"></a>関連項目  
 [関数呼び出し演算子: ()](../cpp/function-call-operator-parens.md)