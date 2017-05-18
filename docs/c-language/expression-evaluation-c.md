---
title: "式の評価 (C) | Microsoft Docs"
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
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
caps.latest.revision: 6
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ec5d4e82d9235f4ef2f83de535b38273c741d29a
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="expression-evaluation-c"></a>式の評価 (C)
代入、単項インクリメント、単項デクリメント、または関数呼び出しが含まれている式は、式の評価に付随する結果 (副作用) が生じる場合があります。 "シーケンス ポイント" に達すると、すべての副作用を含む、シーケンス ポイントより前にあるすべてのものが、シーケンス ポイントより後のものの評価が開始される前に、評価されることが保証されます。  
  
 "副作用" は式の評価による変更です。 副作用は、式の評価によって変数の値が変更されるたびに発生します。 すべての代入演算子に副作用があるわけではありません。 関数呼び出しでは、直接割り当てまたはポインター経由での間接割り当てにより外部から参照できる項目の値を変更すると、副作用が生じることもあります。  
  
## <a name="see-also"></a>関連項目  
 [オペランドおよび式](../c-language/operands-and-expressions.md)
