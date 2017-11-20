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
ms.openlocfilehash: c60932b719b25365c7d8f65a4649ef782a4f9888
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="intrinsics-and-inline-assembly"></a>組み込みおよびインライン アセンブリ
制約の 1 つ、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]コンパイラではインライン アセンブラーのサポートがありません。 関数をすることを意味は、サブルーチン、またはコンパイラによってサポートされる組み込み関数として記述する必要がいずれかの C または C++ で記述することはできません。 特定の関数は、他のユーザーがないときに、パフォーマンスの機密性の高いです。 パフォーマンスが重視される関数は、組み込み関数として実装する必要があります。  
  
 コンパイラでサポートされている組み込み関数は「[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)です。  
  
## <a name="see-also"></a>関連項目  
 [x64 ソフトウェア規約](../build/x64-software-conventions.md)