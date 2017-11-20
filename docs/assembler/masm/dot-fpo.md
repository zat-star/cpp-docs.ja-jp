---
title: ".FPO |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .FPO
dev_langs: C++
helpviewer_keywords: .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fc26358e1da11ada6b23364576bfedb379bc4030
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)