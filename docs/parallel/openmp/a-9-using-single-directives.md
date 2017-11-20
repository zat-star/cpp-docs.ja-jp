---
title: "A.9 を使用する 1 つのディレクティブ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 101d6570f2e3c3e757f28ffb632633d6570dac06
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="a9---using-single-directives"></a>A.9 single ディレクティブの使用
次の例で、`single`ディレクティブ ([セクション 2.4.3](../../parallel/openmp/2-4-3-single-construct.md) [15] ページ)。 例では、1 つのスレッド (通常、最初のスレッドが発生した、`single`ディレクティブ)、進行状況メッセージを出力します。 ユーザー必要があります、どのスレッドは実行するようにどのような想定を行わない、`single`セクションです。 その他のすべてのスレッドはスキップされます、`single`セクションし、最後のバリアを停止、`single`を構築します。 その他のスレッドがスレッドを実行するために待機することがなく続行できないかどうか、 `single`  セクションで、`nowait`に句を指定することができます、`single`ディレクティブです。  
  
```  
#pragma omp parallel  
{  
    #pragma omp single  
        printf_s("Beginning work1.\n");  
    work1();  
    #pragma omp single  
        printf_s("Finishing work1.\n");  
    #pragma omp single nowait  
        printf_s("Finished work1 and beginning work2.\n");  
    work2();  
}  
```