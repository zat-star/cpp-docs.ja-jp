---
title: .FPO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .FPO
dev_langs:
- C++
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76f3fb3d06e3d09cdd63e48ef2ab8a6ce95c81e6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="fpo"></a>.FPO
します。FPO ディレクティブは、.debug' に対する $F セグメントまたはセクションにデバッグ レコードの生成を制御します。  
  
## <a name="syntax"></a>構文  
  
```  
  
FPO (  
cdwLocals  
,   
cdwParams  
,   
cbProlog  
,   
cbRegs  
,   
fUseBP  
,   
cbFrame  
)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cdwLocals`  
 ローカル変数、符号なし 32 ビット値の数です。  
  
 `cdwParams`  
 DWORD、符号なし 16 ビット値では、パラメーターのサイズです。  
  
 *cbProlog*  
 符号なし 8 ビット値、関数プロローグ コードのバイト数。  
  
 `cbRegs`  
 保存されたレジスタを番号します。  
  
 `fUseBP`  
 EBP レジスタが割り当てられているかどうかを示します。 0 または 1 です。  
  
 *cbFrame*  
 フレームの種類を示します。  参照してください[FPO_DATA](http://msdn.microsoft.com/library/windows/desktop/ms679352)詳細についてはします。  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)