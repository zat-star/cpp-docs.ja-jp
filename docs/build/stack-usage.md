---
title: "使用状況をスタック |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d6e3aa8d01dcc85b6c37684ccccaf82c84d8dfb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="stack-usage"></a>スタックの使用
RSP の現在のアドレスを超えるすべてのメモリは不安定なものと見なされます: OS、または、デバッガーは、ユーザーのデバッグ セッションでは、または、割り込みハンドラーの中にこのメモリを上書き可能性があります。 したがって、RSP は常に読み取りまたはスタックのフレームの値の書き込みを試行する前に設定する必要があります。  
  
 このセクションでは、ローカル変数のスタック領域の割り当てを説明し、 **alloca**組み込みです。  
  
-   [スタック割り当て](../build/stack-allocation.md)  
  
-   [動的なパラメーター スタック領域の構成](../build/dynamic-parameter-stack-area-construction.md)  
  
-   [関数の型](../build/function-types.md)  
  
-   [malloc アライメント](../build/malloc-alignment.md)  
  
-   [alloca](../build/alloca.md)  
  
## <a name="see-also"></a>参照  
 [x64 ソフトウェア規約](../build/x64-software-conventions.md)