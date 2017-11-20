---
title: _CIfmod | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CIfmod
apilocation:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- _CIfmod
- CIfmod
dev_langs: C++
helpviewer_keywords:
- CIfmod intrinsic
- _CIfmod intrinsic
ms.assetid: 7c050653-7ec6-4810-b3a7-7a0057ea65ed
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bd1a7f406754f8de985ae5273d7104947a7c7631
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cifmod"></a>_CIfmod
スタックの 2 つのトップ値の浮動小数点の剰余を計算します。  
  
## <a name="syntax"></a>構文  
  
```  
void __cdecl _CIfmod();  
```  
  
## <a name="remarks"></a>コメント  
 このバージョンの `fmod` 関数には、コンパイラで認識される特殊な呼び出し規則があります。 コピーの生成を防ぎ、レジスタ割り当てが容易になるため、実行時間が短縮されます。  
  
 結果の値は、スタックのトップにプッシュされます。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:** x86  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmod、fmodf](../c-runtime-library/reference/fmod-fmodf.md)