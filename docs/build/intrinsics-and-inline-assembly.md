---
title: "組み込みおよびインライン アセンブリ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 80eb16eb7fde49c499227bb3d60000e2ac6e5143
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="intrinsics-and-inline-assembly"></a>組み込みおよびインライン アセンブリ
制約の 1 つ、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]コンパイラではインライン アセンブラーのサポートがありません。 関数をすることを意味は、サブルーチン、またはコンパイラによってサポートされる組み込み関数として記述する必要がいずれかの C または C++ で記述することはできません。 特定の関数は、他のユーザーがないときに、パフォーマンスの機密性の高いです。 パフォーマンスが重視される関数は、組み込み関数として実装する必要があります。  
  
 コンパイラでサポートされている組み込み関数は「[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)です。  
  
## <a name="see-also"></a>参照  
 [x64 ソフトウェア規約](../build/x64-software-conventions.md)