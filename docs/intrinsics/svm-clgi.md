---
title: "_ _svm_clgi |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __svm_clgi
dev_langs: C++
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3fe7aacf6a337235e40c9d681ddce1928fe28c2e
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="svmclgi"></a>__svm_clgi
**Microsoft 固有の仕様**  
  
 グローバル割り込みフラグをクリアします。  
  
## <a name="syntax"></a>構文  
  
```  
void __svm_clgi( void );  
```  
  
## <a name="remarks"></a>コメント  
 `__svm_clgi`関数と同じ、`CLGI`マシン語命令します。 グローバル割り込みフラグかを決定マイクロプロセッサは無視されます、延期、I/O 完了、ハードウェア温度アラート、またはデバッグ例外などのイベントが原因の割り込みを処理します。  
  
 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、ドキュメントの検索"AMD64 アーキテクチャ プログラマの手動ボリューム 2: システム プログラミングでは、"の文書番号 24593、リビジョン、3.11、 [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746)サイトです。  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__svm_clgi`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [__svm_stgi](../intrinsics/svm-stgi.md)