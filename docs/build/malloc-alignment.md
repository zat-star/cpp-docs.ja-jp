---
title: "malloc アライメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a8d1d1b4-5122-456f-9a64-a50e105e55a5
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 66ec1e2e86996b8044909961bef9ab4ea3e76312
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="malloc-alignment"></a>malloc アライメント
[malloc](../c-runtime-library/reference/malloc.md)割り当てられているメモリの量に合わせてでした基本的なアラインメントとを持つ任意のオブジェクトを格納するのに適切に配置されるメモリを返すことが保証されます。 A*基本的なアラインメント*が小さいアラインメント指定せずに実装によってサポートされている最大の配置を配置します。 (Visual C++ の基本的なアラインメントは、`double` つまり 8 バイトに対して必要なアラインメントです。 64 ビット プラットフォームを対象としたコードでは 16 バイトです)。たとえば、4 バイト割り当ての場合、4 バイト以下のオブジェクトをサポートする境界上にアラインメントされます。  
  
 Visual C の許可を持つ型*拡張アラインメント*とも呼ばれるは*オーバーアラインメント*型。 Sse 命令の種類など、 [_ _m128](../cpp/m128.md)と`__m256`、しを使用して宣言されている型`__declspec(align( n ))`場所`n`8 より大きい値は、配置を拡張しました。 オブジェクトで拡張アラインメントが必要な場合、そのオブジェクトに適した境界上でのメモリのアラインメントは、`malloc` によって保証されません。 オーバーア ラインされている型のメモリを割り当てを使用して[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)および関連する関数。  
  
## <a name="see-also"></a>関連項目  
 [スタックの使用](../build/stack-usage.md)   
 [配置](../cpp/align-cpp.md)   
 [__declspec](../cpp/declspec.md)