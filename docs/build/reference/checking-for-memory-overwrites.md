---
title: "メモリ上書きのチェック |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4560fb580d3d1b24feccf84dc07bde7dc38458c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="see-also"></a>関連項目  
 [リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)