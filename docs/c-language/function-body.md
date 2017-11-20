---
title: "関数本体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a30ad1b016e0ab4814e0ac6f6f4627cdf265f59b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="function-body"></a>関数本体
"関数本体" は、関数が何を行うかを指定するステートメントを含む複合ステートメントです。  
  
## <a name="syntax"></a>構文  
 *function-definition*:  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq* は Microsoft 固有の仕様 */  
  
 *compound-statement*: /\* 関数本体 \*/  
 **{**  *declaration-list* opt*statement-list* opt**}**  
  
 関数本体で宣言された変数 ("ローカル変数") は、他の指定がない限り、**auto** ストレージ クラスになります。 関数が呼び出されると、ローカル変数のストレージが作成され、ローカルの初期化が実行されます。 実行制御は、*compound-statement* の最初のステートメントに渡され、`return` ステートメントが実行されるか、関数本体の終端に到達するまで続行されます。 次に、関数が呼び出された位置に制御が戻ります。  
  
 関数が値を返す場合は、式を含む `return` ステートメントを実行する必要があります。 関数の戻り値は、`return` ステートメントが実行されていない場合、または `return` ステートメントが式を含まない場合は未定義です。  
  
## <a name="see-also"></a>関連項目  
 [C 関数の定義](../c-language/c-function-definitions.md)