---
title: "IF (MASM) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: if
dev_langs: C++
helpviewer_keywords: IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6889f70ce149a03adc47fba48e67dc0b9434473c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="if-masm"></a>IF (MASM)
アセンブリの*ifstatements*場合*expression1*が true (ゼロ以外) または*elseifstatements*場合*expression1*が false (0) と*expression2*は true です。  
  
## <a name="syntax"></a>構文  
  
```  
  
   IF expression1  
ifstatements  
[[ELSEIF expression2  
   elseifstatements]]  
[[ELSE  
   elsestatements]]  
ENDIF  
```  
  
## <a name="remarks"></a>コメント  
 次のディレクティブに置き換えられる可能性があります[ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**、 **ELSEIFDEF**、 **ELSEIFDIF**、 **ELSEIFDIFI**、 **ELSEIFE**、 **ELSEIFIDN**、 **ELSEIFIDNI**、 **ELSEIFNB**、および**ELSEIFNDEF**. 必要に応じて、アセンブル*elsestatements*前の式が false の場合。 アセンブリの時に、式が評価されることに注意してください。  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)