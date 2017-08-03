---
title: "C シーケンス ポイント | Microsoft Docs"
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
- sequence points
ms.assetid: c84885a5-4336-4eba-a643-058df4249903
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
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 85e9d8c04280b6f40081b1362a46bf27b62bcc28
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="c-sequence-points"></a>C シーケンス ポイント
連続する "シーケンス ポイント" 間で、オブジェクトの値を一度だけ式によって変更できます。 C 言語では次のシーケンス ポイントが定義されます。  
  
-   論理 AND 演算子 (**&&**) の左オペランド。 論理 AND 演算子の左オペランドは完全に評価され、すべての副作用は続行の前に完了します。 左オペランドが false (0) に評価されると、もう一方のオペランドは評価されません。  
  
-   論理 OR 演算子 (`||`) の左オペランド。 論理 OR 演算子の左オペランドは完全に評価され、すべての副作用は続行の前に完了します。 左オペランドが true (0 以外) に評価されると、もう一方のオペランドは評価されません。  
  
-   コンマ演算子の左オペランド。 コンマ演算子の左オペランドは完全に評価され、すべての副作用は続行の前に完了します。 コンマ演算子のオペランドは両方とも、常に評価されます。 関数呼び出しのコンマ演算子が評価の順序を保証しないことに注意してください。  
  
-   関数呼び出し演算子。 関数のすべての引数が評価され、関数へのエントリ前にすべての副作用が完了します。 引数間の評価順序は指定されていません。  
  
-   条件演算子の最初のオペランド。 条件演算子の最初のオペランドは完全に評価され、すべての副作用は続行の前に完了します。  
  
-   完全な初期化式 (宣言ステートメントの初期化の末尾など、別の式の一部ではない式) の末尾。  
  
-   式ステートメント内の式。 式ステートメントは、省略可能な式とそれに続くセミコロン (**;**) で構成されます。 この式はその副作用のために評価され、この式に続くシーケンス ポイントがあります。  
  
-   選択ステートメント (**if** または `switch`) 内の制御式。 式は完全に評価され、すべての副作用は選択に依存するコードが実行される前に完了します。  
  
-   `while` または **do** ステートメントの制御式。 この式は完全に評価され、`while` または **do** ループの次の反復処理でステートメントが実行される前にすべての副作用が完了します。  
  
-   **for** ステートメントの 3 つの各式。 この式は完全に評価され、**for** ループの次の反復処理でステートメントが実行される前にすべての副作用が完了します。  
  
-   `return` ステートメント内の式。 式は完全に評価され、すべての副作用は呼び出し元の関数に制御が戻る前に完了します。  
  
## <a name="see-also"></a>関連項目  
 [式の評価](../c-language/expression-evaluation-c.md)
