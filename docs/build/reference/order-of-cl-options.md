---
title: "CL オプションの指定順序 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe コンパイラ, 設定 (オプションを)"
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# CL オプションの指定順序
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/link オプション以外のコンパイラ オプションは、コマンド ライン上にどの順序でも指定できます。\/link オプションは、コンパイラ オプションの最後に指定します。  コンパイラを起動すると、まず、[環境変数 CL](../../build/reference/cl-environment-variables.md) に指定したオプションが読み込まれ、次にコマンド ライン上のオプションが左から右の順序で読み込まれます。このとき、コマンド ファイルは指定した順で処理されます。  各オプションは、コマンド ライン上で指定したすべてのファイルに適用されます。  矛盾するオプションがあると、一番右側にあるオプションが適用されます。  
  
## 参照  
 [コンパイラ コマンド ラインの構文](../../build/reference/compiler-command-line-syntax.md)