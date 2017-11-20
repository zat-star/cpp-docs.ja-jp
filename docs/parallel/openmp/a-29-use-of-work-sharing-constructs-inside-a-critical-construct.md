---
title: "A.29 使用の動作共有構築内 critical コンストラクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: d5c8a83f-2f51-4f23-8ddf-d267e347507f
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2aac51541574ee1cf0363a77f40891ac37a18c49
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="a29---use-of-work-sharing-constructs-inside-a-critical-construct"></a>A.29 critical コンストラクト内での work-sharing コンストラクトの使用
次の例では、内部 work-sharing コンス トラクターの使用方法を示します、`critical`を構築します。 この例では準拠作業の共有を作成し、`critical`コンストラクトを同じ並列領域にバインドしないでください。  
  
```  
void f()  
{  
  int i = 1;  
  #pragma omp parallel sections  
  {  
    #pragma omp section  
    {  
      #pragma omp critical (name)  
      {  
        #pragma omp parallel  
        {  
          #pragma omp single  
          {  
            i++;  
          }  
        }  
      }  
    }  
  }  
}  
```