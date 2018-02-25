---
title: "_ _svm_stgi |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __svm_stgi
dev_langs:
- C++
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9346270c09a3174c2583d68cdfb62e11f5112144
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="svmstgi"></a>__svm_stgi
**Microsoft 固有の仕様**  
  
 グローバル割り込みフラグを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
void __svm_stgi(void);  
```  
  
## <a name="remarks"></a>コメント  
 `__svm_stgi`関数と同じ、`STGI`マシン語命令します。 グローバル割り込みフラグかを決定マイクロプロセッサは無視されます、延期、I/O 完了、ハードウェア温度アラート、またはデバッグ例外などのイベントが原因の割り込みを処理します。  
  
 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、ドキュメントの検索"AMD64 アーキテクチャ プログラマの手動ボリューム 2: システム プログラミングでは、"の文書番号 24593、リビジョン、3.11、 [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746)サイトです。  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__svm_stgi`|x86、 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [__svm_clgi](../intrinsics/svm-clgi.md)