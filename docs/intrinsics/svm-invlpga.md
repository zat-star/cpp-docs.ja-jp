---
title: "_ _svm_invlpga |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __svm_invlpga
dev_langs: C++
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f3206fa7f67fcd676b1490c6fad3be9a03c1ea40
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="svminvlpga"></a>__svm_invlpga
**Microsoft 固有の仕様**  
  
 コンピューターの翻訳ルック アサイドのバッファーのアドレス マッピング エントリを無効にします。 パラメーターは、仮想アドレスと無効化するページのアドレス空間の識別子を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
void __svm_invlpga(  
     void *Va,  
     int ASID);  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `Va`|無効化するページの仮想アドレス。|  
|[入力] `ASID`|無効化するページのアドレス空間識別子 (ASID) です。|  
  
## <a name="remarks"></a>コメント  
 `__svm_invlpga`関数と同じ、`INVLPGA`マシン語命令します。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、ドキュメントの検索"AMD64 アーキテクチャ プログラマの手動ボリューム 2: システム プログラミングでは、"の文書番号 24593、リビジョン、3.11、 [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746)サイトです。  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__svm_invlpga`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)