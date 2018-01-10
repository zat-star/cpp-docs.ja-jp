---
title: _CIatan2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CIatan2
apilocation:
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- CIatan2
- _CIatan2
dev_langs: C++
helpviewer_keywords:
- _CIatan2 intrinsic
- CIatan2 intrinsic
ms.assetid: 31f8cc78-b79f-4576-b73b-8add18e08680
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4a3163dcb844892cd4add63c4c985d3742831523
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ciatan2"></a>_CIatan2
*x* / *y* のアーク タンジェントを計算します。*x*と*y* は、スタックの最上位の値です。  
  
## <a name="syntax"></a>構文  
  
```  
void __cdecl _CIatan2();  
```  
  
## <a name="remarks"></a>コメント  
 このバージョンの `atan2` 関数には、コンパイラで認識される特殊な呼び出し規則があります。 コピーの生成を防ぎ、レジスタ割り当てが容易になるため、実行時間が短縮されます。  
  
 結果の値は、スタックのトップにプッシュされます。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:** x86  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [atan、atanf、atanl、atan2、atan2f、atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)