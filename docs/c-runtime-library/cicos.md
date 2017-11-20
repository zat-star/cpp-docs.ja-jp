---
title: _CIcos | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CIcos
apilocation:
- msvcr90.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- CIcos
- _CIcos
dev_langs: C++
helpviewer_keywords:
- _CIcos intrinsic
- CIcos intrinsic
ms.assetid: 6fc203fb-66f3-4ead-9784-f85833c26f1b
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cab375ac2224ff4c3dfc8f66f84b69a5256f388f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cicos"></a>_CIcos
スタックのトップ値のコサインを計算します。  
  
## <a name="syntax"></a>構文  
  
```  
void __cdecl _CIcos();  
```  
  
## <a name="remarks"></a>コメント  
 このバージョンの `cos` 関数には、コンパイラで認識される特殊な呼び出し規則があります。 コピーの生成を防ぎ、レジスタ割り当てが容易になるため、実行時間が短縮されます。  
  
 結果の値は、スタックのトップにプッシュされます。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:** x86  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cos、cosf、cosl、cosh、coshf、coshl](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)