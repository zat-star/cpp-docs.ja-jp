---
title: "式エバリュエーター エラー CXX0064 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0064
dev_langs: C++
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ada57d8df67054fa6577b128a6be73921fbb7e81
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0064"></a>式エバリュエーター エラー CXX0064
バインドされた仮想メンバー関数にブレークポイントを設定することはできません。  
  
 ブレークポイントがなどのオブジェクトへのポインターを介して仮想メンバー関数に設定されました。  
  
```  
pClass->vfunc( int );  
```  
  
 など、クラスを入力して、仮想関数のブレークポイントを設定できます。  
  
```  
Class::vfunc( int );  
```  
  
 このエラーは、can0064 と同じものと同じです。