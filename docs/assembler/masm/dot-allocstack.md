---
title: ".ALLOCSTACK |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .ALLOCSTACK
dev_langs: C++
helpviewer_keywords: .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 20d9147b2c1a95d4fc9600935111a9c0c013be21
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="allocstack"></a>.ALLOCSTACK
生成、 **UWOP_ALLOC_SMALL**または**UWOP_ALLOC_LARGE**プロローグ内の現在のオフセットの指定したサイズでします。  
  
## <a name="syntax"></a>構文  
  
```  
.ALLOCSTACK size  
```  
  
## <a name="remarks"></a>コメント  
 MASM は、指定されたサイズの最も効率的なエンコーディングを選択します。  
  
 .ALLOCSTACK が ml64.exe ユーザー フレーム関数をアンワインドする方法を指定することしから拡張すると、プロローグ内だけで使用されて、 [PROC](../../assembler/masm/proc.md)フレームの宣言、[です。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブです。 これらのディレクティブは、コードを生成しません。のみを生成する`.xdata`と`.pdata`です。 .ALLOCSTACK は、実際にはアンワインドにアクションを実装する命令によって先行されなければなりません。 アンワインド ディレクティブとして、本来はマクロでのアンワインドに同意を得るようにコードの両方をラップすることをお勧めします。  
  
 `size`オペランドが 8 の倍数にする必要があります。  
  
 詳細については、次を参照してください。 [x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)です。  
  
## <a name="sample"></a>サンプル  
 次の例では、アンワインド/例外ハンドラーを指定する方法を示します。  
  
```  
; ml64 ex3.asm /link /entry:Example1  /SUBSYSTEM:Console  
text SEGMENT  
PUBLIC Example3  
PUBLIC Example3_UW  
Example3_UW PROC NEAR  
   ; exception/unwind handler body  
  
   ret 0  
  
Example3_UW ENDP  
  
Example3 PROC FRAME : Example3_UW  
  
   sub rsp, 16  
.allocstack 16  
  
.endprolog  
  
   ; function body  
    add rsp, 16  
   ret 0  
  
Example3 ENDP  
text ENDS  
END  
```  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)