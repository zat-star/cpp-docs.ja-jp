---
title: "NMAKE の致命的なエラー U1070 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1070
dev_langs:
- C++
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5adf5321c96341cfce633a2329a52360be8a45da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1070"></a>NMAKE の致命的なエラー U1070
マクロ定義 'macroname' に循環があります。  
  
 指定されたマクロの定義には、定義に含まれるには、指定されたマクロが含まれているマクロが含まれています。 循環マクロ定義が無効です。  
  
## <a name="example"></a>例  
 次のマクロ定義  
  
```  
ONE=$(TWO)  
TWO=$(ONE)  
```  
  
 次のエラーが発生します。  
  
```  
cycle in macro definition 'TWO'  
```