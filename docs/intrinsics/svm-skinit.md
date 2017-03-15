---
title: "__svm_skinit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_skinit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SKINIT 命令"
  - "__svm_skinit 組み込み"
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_skinit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 仮想マシンのモニターなどおそらく安全なソフトウェアを読み込み開始します。  
  
## 構文  
  
```  
void __svm_skinit(  
   int SLB  
);  
```  
  
#### パラメーター  
  
|パラメーター|Description|  
|------------|-----------------|  
|`SLB`|バイト 32 ビット\) の物理アドレスはローダー ブロックが安全 \(SLB\) です。|  
  
## 解説  
 `__svm_skinit` の関数は `SKINIT` のマシン語命令と同じです。  この関数はプロセッサを使用し確認し読み込むトラス プラットフォーム テッド モジュールがカーネルというセキュリティ \(TPM\) ソフトウェアを信頼したセキュリティ システムの一部です \(SK\)。  仮想マシンのモニターではセキュリティ カーネルの例です。  セキュリティ システムはマルチプロセッサ コンピューターでの初期化処理中に読み込まれるプログラム コンポーネントを確認し割り込みデバイスのアクセスまたは別の改竄するのプログラム コンポーネントを保護します。  
  
 `SLB` のパラメーターは  *安全なローダー ブロックと*  呼ばれるメモリのブロック\) の物理アドレスを指定します \(SLB\)。  SLB はコンピューターのオペレーティング環境を作成しそれを読み込みますカーネル セキュリティが強化されたローダーというプログラムが。  
  
 この関数はゲスト オペレーティング システムとアプリケーションのホスト仮想マシンのモニターの相互作用をサポートします。  詳細については文書の検索「 AMD64 アーキテクチャのプログラマの Manual Volume 2: システム」24593 番目のプログラミングのリビジョン 3.11 [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) を返します。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__svm_skinit`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)