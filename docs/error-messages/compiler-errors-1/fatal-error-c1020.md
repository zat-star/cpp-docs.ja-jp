---
title: "致命的なエラー C1020 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1020
dev_langs: C++
helpviewer_keywords: C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c2689b2526b2cf9dc513052e292aca429113c129
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1020"></a>致命的なエラー C1020
予期しない #endif です。  
  
 `#endif` ディレクティブに対応する `#if`、 `#ifdef`、または `#ifndef` のディレクティブがありません。 各 `#endif` には対応するディレクティブを指定してください。  
  
 次の例では C1020 が生成されます。  
  
```  
// C1020.cpp  
#endif     // C1020  
```  
  
 考えられる解決策:  
  
```  
// C1020b.cpp  
// compile with: /c  
#if 1  
#endif  
```