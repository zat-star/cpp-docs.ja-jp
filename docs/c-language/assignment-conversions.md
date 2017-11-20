---
title: "代入変換 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- conversions, assignment
- assignment conversions
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e51b6af4006ad3d8b35f9167e4db4e3ea84a89f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="assignment-conversions"></a>代入変換
代入演算では、代入値の型が、代入を受け取る変数の型に変換されます。 C では、変換によって情報が失われる場合でも、整数型と浮動小数点型の間で代入による変換を実行できます。 使用される変換メソッドは、「[通常の算術変換](../c-language/usual-arithmetic-conversions.md)」および以下の各セクションで説明されているように、代入に関与する型によって決まります。  
  
-   [符号付き整数型からの変換](../c-language/conversions-from-signed-integral-types.md)  
  
-   [符号なし整数型からの変換](../c-language/conversions-from-unsigned-integral-types.md)  
  
-   [浮動小数点型からの変換](../c-language/conversions-from-floating-point-types.md)  
  
-   [ポインター型との間の変換](../c-language/conversions-to-and-from-pointer-types.md)  
  
-   [他の型からの変換](../c-language/conversions-from-other-types.md)  
  
 型修飾子は変換の許容性には影響しませんが、代入の左辺で **const** 値は使用できません。  
  
## <a name="see-also"></a>関連項目  
 [型変換](../c-language/type-conversions-c.md)