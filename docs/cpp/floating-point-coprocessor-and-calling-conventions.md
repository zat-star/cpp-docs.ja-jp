---
title: "浮動小数点のコプロセッサと呼び出し規約 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "浮動小数点コプロセッサ"
  - "浮動小数点数"
  - "浮動小数点数, コプロセッサ"
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 浮動小数点のコプロセッサと呼び出し規約
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

浮動小数点コプロセッサのアセンブリ ルーチンを作成する場合は、\(関数が ST\(0\) で返す必要がある\) **float** または **double** 値を返していない限り、浮動小数点制御ワードを保持し、コプロセッサ スタックをクリーンする必要があります。  
  
## 参照  
 [呼び出し規約](../Topic/Calling%20Conventions.md)