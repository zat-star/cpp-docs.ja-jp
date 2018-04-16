---
title: "メモリ上書きのチェック |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 573710ae62384c8674009770b3c4fb29100db446
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="checking-for-memory-overwrites"></a>メモリ上書きのチェック
ヒープ操作関数への呼び出しでアクセス違反が発生する場合は、可能であれば、プログラムによって、ヒープが破損していること。 このような状況の一般的な症状は次のようになります。  
  
```  
Access Violation in _searchseg  
```  
  
 [_Heapchk](../../c-runtime-library/reference/heapchk.md)関数は、両方のデバッグで使用可能なビルドとリリース ビルド (Windows NT のみ) のランタイム ライブラリのヒープの整合性を検証します。 使用することができます`_heapchk`とほぼ同じ方法で、`AfxCheckMemory`たとえば、ヒープの上書きを分離する関数。  
  
```  
if(_heapchk()!=_HEAPOK)  
   DebugBreak();  
```  
  
 この関数が失敗した場合、する必要がありますを特定するこの時点で、ヒープが破損しています。  
  
## <a name="see-also"></a>参照  
 [リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)