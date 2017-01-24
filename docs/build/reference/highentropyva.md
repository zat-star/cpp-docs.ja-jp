---
title: "/HIGHENTROPYVA | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/HIGHENTROPYVA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/HIGHENTROPYVA editbin オプション"
  - "HIGHENTROPYVA editbin オプション"
  - "-HIGHENTROPYVA editbin オプション"
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /HIGHENTROPYVA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

実行可能ファイル イメージが高いエントロピの 64 ビット ASLR \(Address Space Layout Randomization\) をサポートするかどうかを指定します。  
  
```  
  
/HIGHENTROPYVA[:NO]  
  
```  
  
## 解説  
 このオプションは、64 ビット アドレスの ASLR がサポートされているかどうかを示す、.dll ファイルまたは .exe ファイルのヘッダーを変更します。  このオプションを実行可能ファイルおよび依存するモジュールのすべてに設定すると、64 ビット ASLR をサポートするオペレーティング システムは、読み込み時に 64 ビットの仮想アドレス空間でランダム化されたアドレスを使用して、実行可能イメージのセグメントのベース アドレスを再設定できます。  この大きいアドレス空間により、攻撃者は特定のメモリ領域の位置を推測することが困難となります。  
  
 既定では、リンカーは 64 ビットの実行可能イメージに対してこのオプションを設定します。  このオプションを設定するには、[\/DYNAMICBASE](../../build/reference/dynamicbase.md) オプションも設定する必要があります。  
  
## 参照  
 [EDITBIN オプション](../../build/reference/editbin-options.md)   
 [\/DYNAMICBASE](../../build/reference/dynamicbase.md)   
 [Windows ISV Software Security Defenses](http://msdn.microsoft.com/library/bb430720.aspx)