---
title: "コンパイラの警告 (レベル 1) C4076 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4076
dev_langs: C++
helpviewer_keywords: C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7918ae093210c38bacfe89f0d4770eda2dee2e35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4076"></a>コンパイラの警告 (レベル 1) C4076
'typemod' : 'typename' 型とは使用できません  
  
 型修飾子は、 **signed** か `unsigned`かにかかわらず、整数以外の型とは使用できません。 ***typemod*** は無視されます。  
  
## <a name="example"></a>例  
 次の例では C4076 が生成されます。  
  
```  
// C4076.cpp  
// compile with: /W1 /LD  
unsigned double x;   // C4076  
```