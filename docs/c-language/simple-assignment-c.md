---
title: "単純な代入 (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- type conversion [C++], simple assignment
- data type conversion [C++], simple assignment
- operators [C], simple assignment
- assignment operators [C++], simple
- simple assignment operator
- equal sign
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: a60ec2f6f6466b579f917d02dabc24736c5a2e92
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="simple-assignment-c"></a>単純な代入 (C)
単純な代入演算子は左オペランドに右オペランドを代入します。 右オペランドの値は、代入式の型に変換され、左オペランドで指定されたオブジェクトに格納されている値を置き換えます。 代入の変換規則が適用されます (「[代入の変換](../c-language/assignment-conversions.md)」を参照)。  
  
```  
double x;  
int y;  
  
x = y;  
```  
  
 この例では、`y` の値は **double** 型に変換され、`x` に割り当てます。  
  
## <a name="see-also"></a>関連項目  
 [C の代入演算子](../c-language/c-assignment-operators.md)
