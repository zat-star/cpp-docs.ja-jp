---
title: "式エバリュエーター エラー CXX0064 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0064
dev_langs:
- C++
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2edeb05e39c6d2e70cb2c9dde562a89e85921301
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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