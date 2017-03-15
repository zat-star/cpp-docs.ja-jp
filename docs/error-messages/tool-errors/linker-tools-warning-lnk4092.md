---
title: "リンカー ツールの警告 LNK4092 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4092
dev_langs:
- C++
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 64d4e7a96009f8b3f2de1ee83f143427542ded65
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4092"></a>リンカー ツールの警告 LNK4092
共有書き込みセクション 'section' には、再配置; が含まれています。イメージは正しく動作しない可能性があります。  
  
 リンカーは、共有のセクションを警告する可能性がある重大な問題がある場合、この警告を出力します。  
  
 複数のプロセス間でデータを&1; つの方法は、セクションに「共有」のマークを付けます ただし、共有セクションをマークすると問題が発生することができます。 たとえば、共有データ セクションに次のように宣言を含む DLL があります。  
  
```  
int var = 1;  
int *pvar = &var;  
```  
  
 リンカーが解決できない`pvar`のため、その値は、DLL がメモリに読み込まれてに依存するのでデータ投入を再配置レコード DLL です。 メモリのアドレスに DLL が読み込まれるときに`var`解決できると`pvar`割り当てられています。 別のプロセスは同じ DLL を読み込みますが、同時に読み込むことができない場合に対処するのアドレスでの再配置`var`間違った住所にポイントが&2; 番目のプロセスと最初のプロセスのアドレス空間が更新されます。
