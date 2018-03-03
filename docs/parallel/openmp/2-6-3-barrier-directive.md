---
title: "2.6.3 barrier ディレクティブ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d9c64787d9c6cc2dd0809f75f8f9db9819174d0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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