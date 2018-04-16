---
title: ".SAFESEH |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .SAFESEH
dev_langs:
- C++
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69212e7a3542a6b6ac88ccbe2ecbbf8894862e65
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="safeseh"></a>.SAFESEH
構造化例外ハンドラーとして関数を登録します。  
  
## <a name="syntax"></a>構文  
  
```  
  
.SAFESEH identifier  
```  
  
## <a name="remarks"></a>コメント  
 *識別子*の ID をローカルに定義されている必要があります[PROC](../../assembler/masm/proc.md)または[EXTRN](../../assembler/masm/extrn.md)プロシージャ A[ラベル](../../assembler/masm/label-masm.md)は許可されていません。 します。SAFESEH ディレクティブに必要な[/safeseh](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml.exe コマンド ライン オプションです。  
  
 構造化例外ハンドラーの詳細については、次を参照してください。 [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)です。  
  
 たとえば、安全な例外ハンドラーを登録するに (次のように) 新しい MASM ファイルを作成、/safeseh でアセンブリおよびリンクされたオブジェクトに追加します。  
  
```  
.386  
.model  flat  
MyHandler   proto  
.safeseh    MyHandler  
end  
```  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)