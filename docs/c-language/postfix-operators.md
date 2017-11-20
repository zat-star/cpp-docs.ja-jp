---
title: "後置演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- operators [C], postfix
- postfix operators
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9ad53a3993bfc55b51cab05d5eca1a10d44bd2c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="postfix-operators"></a>後置演算子
後置演算子は、式の評価で優先順位が最高位 (最も強力なバインディング) になります。  
  
## <a name="syntax"></a>構文  
 *postfix-expression*:  
 *primary-expression*  
  
 *postfix-expression*  **[**  *expression*  **]**  
  
 *postfix-expression*  **(**  *argument-expression-list* opt**)**  
  
 *postfix-expression*  **.**  *identifier*  
  
 *postfix-expression*  **->**  *identifier*  
  
 *postfix-expression*  **++**  
  
 *postfix-expression*  **--**  
  
 この優先順位レベルの演算子は、配列の添字、関数呼び出し、構造体/共用体メンバー、および後置インクリメント/デクリメント演算子です。  
  
## <a name="see-also"></a>関連項目  
 [C 演算子](../c-language/c-operators.md)