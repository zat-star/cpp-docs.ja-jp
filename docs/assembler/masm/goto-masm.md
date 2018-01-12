---
title: "GOTO (MASM) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: goto
dev_langs: C++
helpviewer_keywords: GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed7e20bb7f81b74a2f670e604e958ca02f132531
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="goto-masm"></a>GOTO (MASM)
マークされた行にアセンブリを転送**:***macrolabel*です。  
  
## <a name="syntax"></a>構文  
  
```  
  
GOTO   
macrolabel  
  
```  
  
## <a name="remarks"></a>コメント  
 **GOTO**内でのみ使用[マクロ](../../assembler/masm/macro.md)、[の](../../assembler/masm/for-masm.md)、 [FORC](../../assembler/masm/forc.md)、[繰り返します](../../assembler/masm/repeat.md)、および**中に**ブロックします。 ラベルは、行で唯一のディレクティブをする必要があります、先頭のコロンの前にする必要があります。  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)