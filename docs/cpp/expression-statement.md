---
title: "式ステートメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e627e107df850f31a9cf04981795edd1185c0ce5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="expression-statement"></a>式ステートメント
式ステートメントを使用すると、式が評価されます。 式ステートメントの結果として、制御が移動したり、イテレーションが発生したりすることはありません。  
  
 式ステートメントの構文は、次のように、単純です。  
  
## <a name="syntax"></a>構文  
  
```  
[expression ] ;  
```  
  
## <a name="remarks"></a>コメント  
 式ステートメント内の式はすべて評価され、次のステートメントが実行される前にすべての副作用が完了します。 最も一般的に使用される式ステートメントは、代入と関数呼び出しです。  式はオプションなのでと呼ばれる、空の式ステートメントがセミコロンだけでと見なされます、 [null](../cpp/null-statement.md)ステートメントです。  
  
## <a name="see-also"></a>参照  
 [C++ ステートメントの概要](../cpp/overview-of-cpp-statements.md)