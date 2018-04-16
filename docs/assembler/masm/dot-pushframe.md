---
title: ".PUSHFRAME |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .PUSHFRAME
dev_langs:
- C++
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8fa9b03f1075418019f41f3d537607372bf8d498
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="pushframe"></a>.PUSHFRAME
生成、`UWOP_PUSH_MACHFRAME`アンワインド コードのエントリ。 場合、省略可能な`code`を指定すると、アンワインド コードのエントリが 1 の修飾子を指定します。 それ以外の場合、修飾子には 0 です。  
  
## <a name="syntax"></a>構文  
  
```  
.PUSHFRAME [code]  
```  
  
## <a name="remarks"></a>コメント  
 .PUSHFRAME が ml64.exe ユーザー フレーム関数をアンワインドする方法を指定することしから拡張すると、プロローグ内だけで使用されて、 [PROC](../../assembler/masm/proc.md)フレームの宣言、[です。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブです。 これらのディレクティブは、コードを生成しません。のみを生成する`.xdata`と`.pdata`です。 .PUSHFRAME は、実際にはアンワインドにアクションを実装する命令によって先行されなければなりません。 アンワインド ディレクティブとして、本来はマクロでのアンワインドに同意を得るようにコードの両方をラップすることをお勧めします。  
  
 詳細については、次を参照してください。 [x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)です。  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)