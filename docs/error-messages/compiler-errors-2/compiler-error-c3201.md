---
title: "コンパイラ エラー C3201 | Microsoft Docs"
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
  - "C3201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3201"
ms.assetid: ec19cd64-1789-40a3-b2db-dff2852b9d98
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

クラス テンプレート 'template' 用テンプレート パラメーター リストが、テンプレート パラメーター 'template' 用テンプレート パラメーター リストと一致しません。  
  
 テンプレート パラメーターを受け取らないクラス テンプレートに引数のクラス テンプレートが渡されました。または、既定のテンプレート引数にテンプレート引数と一致しない数値が渡されました。  
  
```  
// C3201.cpp  
template<typename T1, typename T2>  
class X1  
{  
};  
  
template<template<typename T> class U = X1>   // C3201  
class X2  
{  
};  
  
template<template<typename T, typename V> class U = X1>   // OK  
class X3  
{  
};  
```