---
title: "_enable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_enable"
  - "_enable_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_enable intrinsic"
  - "enable intrinsic"
  - "ssm instruction"
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _enable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 割り込みを有効にします。  
  
## 構文  
  
```  
void _enable(void);  
```  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`_enable`|x86、ARM、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 `_enable` は、プロセッサに対して割り込みフラグを設定するように指示します。  x86 システムでは、この関数は割り込みフラグの設定 \(`sti`\) 命令を生成します。  
  
 この関数はカーネル モードのみで使用できます。  ユーザー モードで使用した場合は、特権命令例外がスローされます。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)