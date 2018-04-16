---
title: "_ _svm_vmrun |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __svm_vmrun
dev_langs:
- C++
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 988a045bc957d5920fee7e3e659d7a0b4f02d8d2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="svmvmrun"></a>__svm_vmrun
**Microsoft 固有の仕様**  
  
 指定された仮想マシン制御ブロック (VMCB) に対応する仮想マシンのゲスト コードの実行を開始します。  
  
## <a name="syntax"></a>構文  
  
```  
void __svm_vmrun(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `VmcbPhysicalAddress`|VMCB の物理アドレス。|  
  
## <a name="remarks"></a>コメント  
 `__svm_vmrun`関数は、仮想マシンのゲスト コードの実行を開始するため、VMCB で最小限の情報を使用します。 使用して、 [_ _svm_vmsave](../intrinsics/svm-vmsave.md)または[_ _svm_vmload](../intrinsics/svm-vmload.md)関数の詳細については複雑な割り込みを処理するか、別のゲストに切り替える必要とする場合。  
  
 `__svm_vmrun`関数と同じ、`VMRUN`マシン語命令します。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、ドキュメントの検索"AMD64 アーキテクチャ プログラマの手動ボリューム 2: システム プログラミングでは、"ドキュメント番号 24593、3.11 またはそれ以降でのリビジョン、 [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746)サイトです。  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__svm_vmrun`|x86、 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [__svm_vmsave](../intrinsics/svm-vmsave.md)   
 [__svm_vmload](../intrinsics/svm-vmload.md)