---
title: "コンパイラの警告 (レベル 1) C4124 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4124
dev_langs:
- C++
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
caps.latest.revision: 6
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8f367d8ec2360939d499c9f4e53ee690f860cc18
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4124"></a>コンパイラの警告 (レベル 1) C4124
キーワード __fastcall が使われましたが スタックチェッキングがあるため低速コードになります。  
  
 `__fastcall`スタック チェックが有効でキーワードが使用されました。  
  
 `__fastcall`規則には、高速なコードが生成されますが、低速のコードをスタック チェックします。 使用する場合`__fastcall`、スタックを使用してチェックをオフにする、 **check_stack**プラグマまたは/Gs します。  
  
 これらの条件下で宣言されている&1; つ目の関数にのみ警告が表示されます。
