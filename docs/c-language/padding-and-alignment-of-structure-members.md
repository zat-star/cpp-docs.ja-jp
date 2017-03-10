---
title: "構造体メンバーの埋め込みとアライメント | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- structure members, padding and alignment
ms.assetid: c999820b-dd47-41fc-b923-e4c7ebbcd30f
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 1d2a2c895e636937781c6068e8f3c8816e8814a5
ms.lasthandoff: 02/24/2017

---
# <a name="padding-and-alignment-of-structure-members"></a>Padding and Alignment of Structure Members (構造体メンバーのパディングとアラインメント)
**ANSI 3.5.2.1** 構造体のメンバーの埋め込みとアラインメント、およびビット フィールドがストーレジ単位境界をまたげるかどうか  
  
 構造体メンバーは、宣言されている順に格納され、最初のメンバーが最も下位のメモリ アドレスを、最後のメンバーが最も上位のアドレスを持ちます。  
  
 データ オブジェクトにはそれぞれ、alignment-requirement (アラインメント要件) があります。 構造体、共用体、配列を除くすべてのデータのアラインメント要件は、オブジェクトのサイズまたは現在のパッキング サイズです (パッキング サイズは /Zp または `pack` プラグマで指定され、いずれか小さい方が適用されます)。 構造体、共用体、配列の場合、アラインメント要件はそのメンバーの最大のアラインメント要件になります。 すべてのオブジェクトには、次の式を満たすように offset (オフセット) が割り当てられます。  
  
 *offset*  `%` *alignment-requirement* `==` 0  
  
 隣接するビット フィールドは、同じサイズの整数型で、次のビット フィールドがビット フィールドの共通のアラインメント要件によって課される境界を越えずに現在の割り当て単位に収まる場合は、同じ 1、2、または 4 バイトの割り当て単位にパックされます。  
  
## <a name="see-also"></a>関連項目  
 [構造体、共用体、列挙体、ビット フィールド](../c-language/structures-unions-enumerations-and-bit-fields.md)
