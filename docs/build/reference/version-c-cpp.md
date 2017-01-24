---
title: "VERSION (C/C++) | Microsoft Docs"
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
  - "VERSION"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VERSION ステートメント (.def ファイル)"
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# VERSION (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

.exe ファイルまたは DLL ファイルのヘッダーに数値を書き込むように LINK に指示します。  
  
```  
VERSION major[.minor]  
```  
  
## 解説  
 引数 *major* と引数 *minor* には 0 ～ 65,535 の 10 進数値を指定します。  既定では、バージョン 0.0 になります。  
  
 コマンド ラインでバージョン番号を指定するには、[\/VERSION \(バージョン情報\)](../Topic/-VERSION%20\(Version%20Information\).md) オプションを使用します。  
  
## 参照  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)