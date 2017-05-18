---
title: "致命的なエラー C1022 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1022
dev_langs:
- C++
helpviewer_keywords:
- C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: c975e7ffc3e70905dba238bd8e1161b71cd83857
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1022"></a>致命的なエラー C1022
#endif が必要です。  
  
 `#if`、 `#ifdef`、 `#ifndef` の各ディレクティブに対応する `#endif` ディレクティブがありません。 各 `#if`、 `#ifdef`、 `#ifndef` に対応する `#endif`を指定してください。  
  
 次の例では C1022 が生成されます。  
  
```  
// C1022.cpp  
#define true 1  
  
#if (true)  
#else   
#else    // C1022  
```  
  
 考えられる解決策:  
  
```  
// C1022b.cpp  
// compile with: /c  
#define true 1  
  
#if (true)  
#else   
#endif  
```
