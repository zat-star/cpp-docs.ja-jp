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
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad065eb3f35080ff2e5743c0259b20ba72ee6175
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2018
---
# <a name="obsolete-calling-conventions"></a>廃止された呼び出し規則
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 **_ _Pascal**、 **_ _fortran**、および**_ _syscall**呼び出し規約はサポートされていません。 サポートされる呼び出し規則および適切なリンカー オプションの 1 つを使用して、それらの機能をエミュレートできます。  
  
 \<windows.h > ようになりました、 **WINAPI**マクロで、ターゲットの適切な呼び出し規約に変換します。 使用して**WINAPI**場所を使用していた**PASCAL**または**__far \__pascal**です。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)