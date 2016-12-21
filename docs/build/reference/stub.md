---
title: "STUB | Microsoft Docs"
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
  - "STUB"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STUB ステートメント (.def ファイル)"
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# STUB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

仮想デバイス ドライバー \(VxD\) をビルドするモジュール定義ファイルで STUB を使用すると、既定のヘッダーではなく、VxD で使われる IMAGE\_DOS\_HEADER 構造体 \(WINNT.H で定義されている\) を含むファイル名を指定できます。  
  
```  
STUB:filename  
```  
  
## 解説  
 *filename* は、[\/STUB](../../build/reference/stub-ms-dos-stub-file-name.md) リンカー オプションで指定することもできます。  
  
 STUB は、VxD をビルドする場合にだけ、モジュール定義ファイルで使用できます。  
  
## 参照  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)