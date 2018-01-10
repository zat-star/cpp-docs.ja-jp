---
title: "Barrier ディレクティブのバインディングを A.20 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5b8cc2799f0aea9e75b3aad44d3cfa9e3f5e7de4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="a20---binding-of-barrier-directives"></a>A.20 barrier ディレクティブのバインド
ディレクティブのバインディングのルールの呼び出し、**バリア**、最も近い包含にバインドするディレクティブ`parallel`ディレクティブです。 ディレクティブのバインディングの詳細については、次を参照してください。[セクション 2.8](../../parallel/openmp/2-8-directive-binding.md) [32] ページ。  
  
 呼び出し、次の例で*メイン*に*sub2*が準拠しているため、**バリア**(で*sub3*) 並列領域にバインド*sub2*です。 呼び出し*メイン*に*sub1*は準拠していませんので、**バリア**サブルーチンで並列領域にバインド*sub2*です。  呼び出し*メイン*に*sub3*が準拠しているため、**バリア**の並列領域にバインドしないと、無視されます。 またを注意してください、**バリア**のみチーム、外側の並行領域内のスレッドとで作成されたすべてのスレッドの同期をとる*sub1*です。  
  
```  
int main()  
{  
    sub1(2);  
    sub2(2);  
    sub3(2);  
}  
  
void sub1(int n)  
{  
    int i;  
    #pragma omp parallel private(i) shared(n)  
    {  
        #pragma omp for  
        for (i=0; i<n; i++)  
            sub2(i);  
    }  
}  
  
void sub2(int k)  
{  
     #pragma omp parallel shared(k)  
     sub3(k);  
}  
  
void sub3(int n)  
{  
    work(n);  
    #pragma omp barrier  
    work(n);  
}  
```