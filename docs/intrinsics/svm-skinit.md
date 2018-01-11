---
title: "_ _svm_skinit |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __svm_skinit
dev_langs: C++
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e02bafc9319a6a3a4c5e07b46c9da6586f440d59
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="svmskinit"></a>__svm_skinit
**Microsoft 固有の仕様**  
  
 仮想マシンのモニターなど、検証可能なセキュリティで保護されたソフトウェアの読み込みを開始します。  
  
## <a name="syntax"></a>構文  
  
```  
void __svm_skinit(  
   int SLB  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`SLB`|64 K バイトの 32 ビットの物理アドレスをセキュリティで保護ローダー ブロック (SLB)。|  
  
## <a name="remarks"></a>コメント  
 `__svm_skinit`関数と同じ、`SKINIT`マシン語命令します。 この関数は、プロセッサおよび信頼されたプラットフォーム モジュール (TPM) を確認し、セキュリティ カーネル (SK) と呼ばれる信頼されているソフトウェアのロードを使用したセキュリティ システムの一部です。 仮想マシンのモニターは、セキュリティのカーネルの例を示します。 セキュリティ システムは、プログラム コンポーネントが初期化プロセス中に読み込まれ、コンポーネントをマルチプロセッサ コンピューターの場合は、割り込み、デバイスのアクセス、または別のプログラムによる改ざんから保護を確認します。  
  
 `SLB`パラメーターと呼ばれるメモリの 64 K のブロックの物理アドレスを指定、*ローダーのブロックをセキュリティで保護された*(SLB)。 SLB には、セキュリティで保護されたローダーをコンピューターの動作環境を確立し、後でセキュリティ カーネルを読み込むと呼ばれるプログラムが含まれています。  
  
 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、ドキュメントの検索"AMD64 アーキテクチャ プログラマの手動ボリューム 2: システム プログラミングでは、"の文書番号 24593、リビジョン、3.11、 [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746)サイトです。  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__svm_skinit`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)