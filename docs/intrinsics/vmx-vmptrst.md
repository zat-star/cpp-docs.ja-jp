---
title: __vmx_vmptrst | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __vmx_vmptrst
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmptrst intrinsic
- VMPTRST instruction
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a08626cd6238df51ee149cc7bf8d873b993fb95e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="vmxvmptrst"></a>__vmx_vmptrst
**Microsoft 固有の仕様**  
  
 指定したアドレスに現在の仮想マシン制御構造 (VMCS) へのポインターを格納します。  
  
## <a name="syntax"></a>構文  
  
```  
void __vmx_vmptrst(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [in] *`VmcsPhysicalAddress`  
 現在 VMCS のポインターが格納されているアドレスです。  
  
## <a name="remarks"></a>コメント  
 VMCS のポインターは、64 ビットの物理アドレスです。  
  
 `__vmx_vmptrst`関数と同じ、`VMPTRST`マシン語命令します。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、「Intel 仮想化技術仕様の「ia-32 Intel アーキテクチャ」、ドキュメントの検索に番号 C97063 002 を文書化、 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127)サイトです。  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__vmx_vmptrst`|x86、 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)