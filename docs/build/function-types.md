---
title: "関数の型 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 7e33d5f4-dabb-406d-afb3-13777b995028
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d43daef2095fb63bd79644c940627754e00e199b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="function-types"></a>関数の型
基本的には、関数の 2 つの種類があります。 スタック フレームを必要とする関数には、フレームの関数は呼び出されます。 スタック フレームを必要としない関数には、リーフ関数は呼び出されます。  
  
 フレームの関数は、スタック領域の割り当て、他の関数を呼び出す、不揮発性レジスタの保存または例外処理を使用する関数です。 関数のテーブルのエントリも必要です。 フレームの関数は、プロローグとエピローグが必要です。 フレームの関数では、スタック領域を動的に割り当てることができます、フレーム ポインターを使用できます。 フレーム関数が呼び出し、破棄された時点の標準のすべての機能を持ちます。  
  
 フレームの関数が別の関数を呼び出さないかどうかは、スタックを整列する必要はありません (セクションで言及[スタック割り当て](../build/stack-allocation.md))。  
  
 リーフ関数は、いずれかの関数のテーブルのエントリを必要としません。 任意の関数またはスタック領域の割り当てできないということを意味する RSP を含め、不揮発性レジスタに変更ができません。 実行時に、スタックのアライメントされていないままにすることができます。  
  
## <a name="see-also"></a>関連項目  
 [スタックの使用](../build/stack-usage.md)
