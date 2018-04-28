---
title: GOTO (MASM) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9eecdab2fe91de0aae656b37c6fddafe658e60c0
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
---
# <a name="goto-masm"></a>GOTO (MASM)
マークされた行にアセンブリを転送 **: * * * macrolabel*です。  
  
## <a name="syntax"></a>構文  
  
```  
  
GOTO   
macrolabel  
  
```  
  
## <a name="remarks"></a>コメント  
 **GOTO**内でのみ使用[マクロ](../../assembler/masm/macro.md)、[の](../../assembler/masm/for-masm.md)、 [FORC](../../assembler/masm/forc.md)、[繰り返します](../../assembler/masm/repeat.md)、および**中に**ブロックします。 ラベルは、行で唯一のディレクティブをする必要があります、先頭のコロンの前にする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)