---
title: "廃止された呼び出し規約 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __fortran
- __pascal
- __syscall
dev_langs:
- C++
helpviewer_keywords:
- WINAPI
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 90f328552677bc0f41accc316433365467dd7673
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="obsolete-calling-conventions"></a>廃止された呼び出し規則
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 **_ _Pascal**、 **_ _fortran**、および**_ _syscall**呼び出し規約はサポートされていません。 サポートされる呼び出し規則および適切なリンカー オプションの 1 つを使用して、それらの機能をエミュレートできます。  
  
 WINDOWS です。H サポートしている、 **WINAPI**マクロで、ターゲットの適切な呼び出し規約に変換します。 使用して**WINAPI**場所を使用していた**PASCAL**または**__far \__pascal**です。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)
