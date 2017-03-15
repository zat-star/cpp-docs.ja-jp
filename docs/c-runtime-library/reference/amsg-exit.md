---
title: "_amsg_exit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_amsg_exit"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_amsg_exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_amsg_exit"
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# _amsg_exit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定したランタイム エラー メッセージが表示され、エラー コード 255 のアプリケーションを終了します。  
  
## 構文  
  
```cpp  
void _amsg_exit (  
   int rterrnum  
   )  
  
```  
  
#### パラメーター  
 `rterrnum`  
 システム定義のランタイム エラー メッセージの ID 番号。  
  
## 解説  
 この関数は、コンソール アプリケーションの **stderr** にランタイム エラー メッセージを出力するか、または Windows アプリケーションを閉じるためのメッセージ ボックスのメッセージが表示されます。  デバッグ モードでは、終了する前にデバッガーを呼び出すこともできます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|\_amsg\_exit|internal.h|