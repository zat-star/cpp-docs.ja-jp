---
title: "式エバリュエーター エラー CXX0064 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0064"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0064"
  - "CXX0064"
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 式エバリュエーター エラー CXX0064
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

仮想メンバーにバインドされた関数にはブレークポイントを設定できません  
  
 オブジェクトへのポインターを通じて、仮想メンバー関数に対するブレークポイントが設定されました。例を次に示します。  
  
```  
pClass->vfunc( int );  
```  
  
 仮想関数に対するブレークポイントは、次のようにクラスを指定することによって設定できます。  
  
```  
Class::vfunc( int );  
```  
  
 このエラーは CAN0064 と同じものです。