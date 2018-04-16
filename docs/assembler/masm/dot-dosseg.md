---
title: .DOSSEG | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .DOSSEG
dev_langs:
- C++
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 39f02937ed1613cbd759621b2a4e75f84db918cf
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="dosseg"></a>.DOSSEG
MS-DOS セグメントの規則に従ってセグメントを並べ替えます。 コードは、最初に、タ、ではなく、セグメントと、タにし、セグメント。  
  
## <a name="syntax"></a>構文  
  
```  
  
.DOSSEG  
  
```  
  
## <a name="remarks"></a>コメント  
 タ内のセグメントが、この順序に従う: BSS やスタックではなくセグメント BSS セグメントし、最後にスタック セグメント。 MASM のスタンドアロン プログラムで CodeView サポートを確保するため、主に使用します。 同じ[DOSSEG](../../assembler/masm/dosseg.md)です。  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)