---
title: "関数本体 | Microsoft Docs"
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
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
caps.latest.revision: 8
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
ms.openlocfilehash: a73f66ed65754897017af40988522e344c725a7c
ms.lasthandoff: 02/24/2017

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
