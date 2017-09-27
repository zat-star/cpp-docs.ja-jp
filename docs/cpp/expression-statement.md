---
title: "式ステートメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements, expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: b48bf6d0dfd1c1ce29d1d116a77d3445bd5e1e30
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

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
  
## <a name="see-also"></a>関連項目  
 [C++ ステートメントの概要](../cpp/overview-of-cpp-statements.md)
