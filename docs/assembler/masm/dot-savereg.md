---
title: ".SAVEREG |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .SAVEREG
dev_langs: C++
helpviewer_keywords: .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ab1e777aa8bdddc4aa4fd71212f3275231b92dc4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="savereg"></a>.SAVEREG
いずれかが生成されます、`UWOP_SAVE_NONVOL`または`UWOP_SAVE_NONVOL_FAR`アンワインド コードのエントリの指定した登録 (`reg`) とオフセット (`offset`) プロローグの現在のオフセットを使用します。 MASM は、最も効率的なエンコーディングを選択します。  
  
## <a name="syntax"></a>構文  
  
```  
.SAVEREG reg, offset  
```  
  
## <a name="remarks"></a>コメント  
 .SAVEREG が ml64.exe ユーザー フレーム関数をアンワインドする方法を指定することしから拡張すると、プロローグ内だけで使用されて、 [PROC](../../assembler/masm/proc.md)フレームの宣言、[です。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブです。 これらのディレクティブは、コードを生成しません。のみを生成する`.xdata`と`.pdata`です。 .SAVEREG は、実際にはアンワインドにアクションを実装する命令によって先行されなければなりません。 アンワインド ディレクティブとして、本来はマクロでのアンワインドに同意を得るようにコードの両方をラップすることをお勧めします。  
  
 詳細については、次を参照してください。 [x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)です。  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)