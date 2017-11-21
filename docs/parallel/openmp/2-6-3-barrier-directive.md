---
title: "2.6.3 barrier ディレクティブ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: adc480a82668da3c3ad7fdb88a701b3fa80ae9e3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="263-barrier-directive"></a>2.6.3 barrier ディレクティブ
**バリア**ディレクティブは、チーム内のすべてのスレッドを同期します。 発生した場合、チーム内の各スレッドはすべて、他のユーザーのこのポイントに到達するまで待機します。 構文、**バリア**ディレクティブは、次のようにします。  
  
```  
#pragma omp barrier new-line  
```  
  
 チームのすべてのスレッドがバリアを検出した後、チーム内の各スレッドは並列 barrier ディレクティブの後、ステートメントの実行を開始します。 ため、**バリア**ディレクティブには、その構文の一部として、C 言語のステートメントはありません、プログラム内で配置する場合に制限があります。 参照してください[付録 C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)正式な文法にします。 次の例は、これらの制限を示しています。  
  
```  
/* ERROR - The barrier directive cannot be the immediate  
*          substatement of an if statement  
*/  
if (x!=0)  
   #pragma omp barrier  
...  
  
/* OK - The barrier directive is enclosed in a  
*      compound statement.  
*/  
if (x!=0) {  
   #pragma omp barrier  
}  
```