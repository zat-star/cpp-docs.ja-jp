---
title: ".SAVEXMM128 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .SAVEXMM128
dev_langs: C++
helpviewer_keywords: .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 384615a0c58c3c28a2e0958d6909546f5753ce6e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="savexmm128"></a>.SAVEXMM128
生成するか、`UWOP_SAVE_XMM128`または`UWOP_SAVE_XMM128_FAR`アンワインド コードのエントリの指定の XMM レジスタと現在のプロローグのオフセットを使用してオフセットします。 MASM は、最も効率的なエンコーディングを選択します。  
  
## <a name="syntax"></a>構文  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## <a name="remarks"></a>コメント  
 .SAVEXMM128 できる ml64.exe フレーム関数をアンワインドするとはから拡張すると、プロローグ内でのみ使用する方法を指定、 [PROC](../../assembler/masm/proc.md)フレームの宣言、[です。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブです。 これらのディレクティブは、コードを生成しません。のみを生成する`.xdata`と`.pdata`です。 .SAVEXMM128 は、実際にはアンワインドにアクションを実装する命令によって先行されなければなりません。 アンワインド ディレクティブとして、本来はマクロでのアンワインドに同意を得るようにコードの両方をラップすることをお勧めします。  
  
 `offset`16 の倍数である必要があります。  
  
 詳細については、次を参照してください。 [x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)です。  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)