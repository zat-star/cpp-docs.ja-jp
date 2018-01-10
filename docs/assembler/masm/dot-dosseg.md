---
title: ".DOSSEG |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .DOSSEG
dev_langs: C++
helpviewer_keywords: .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a53159911c47d1c88df90c53f3302f813e5bd95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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