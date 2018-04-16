---
title: .SAVEXMM128 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .SAVEXMM128
dev_langs:
- C++
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e163f71b0c1d49f845cc871a26d4ee369843597
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="savexmm128"></a>.SAVEXMM128
生成するか、`UWOP_SAVE_XMM128`または`UWOP_SAVE_XMM128_FAR`アンワインド コードのエントリの指定の XMM レジスタと現在のプロローグのオフセットを使用してオフセットします。 MASM は、最も効率的なエンコーディングを選択します。  
  
## <a name="syntax"></a>構文  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## <a name="remarks"></a>コメント  
 .SAVEXMM128 できる ml64.exe フレーム関数をアンワインドするとはから拡張すると、プロローグ内でのみ使用する方法を指定、 [PROC](../../assembler/masm/proc.md)フレームの宣言、[です。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブです。 これらのディレクティブは、コードを生成しません。のみを生成する`.xdata`と`.pdata`です。 .SAVEXMM128 は、実際にはアンワインドにアクションを実装する命令によって先行されなければなりません。 アンワインド ディレクティブとして、本来はマクロでのアンワインドに同意を得るようにコードの両方をラップすることをお勧めします。  
  
 `offset` 16 の倍数である必要があります。  
  
 詳細については、次を参照してください。 [x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)です。  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)