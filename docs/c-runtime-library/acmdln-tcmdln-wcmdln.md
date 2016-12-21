---
title: "_acmdln, _tcmdln, _wcmdln | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcmdln"
  - "_acmdln"
apilocation: 
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_acmdln"
  - "acmdln"
  - "_wcmdln"
  - "wcmdln"
  - "_tcmdln"
  - "tcmdln"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_acmdln グローバル変数"
  - "_tcmdln グローバル変数"
  - "_wcmdln グローバル変数"
  - "acmdln グローバル変数"
  - "tcmdln グローバル変数"
  - "wcmdln グローバル変数"
ms.assetid: 4fc0a6a0-3f93-420a-a19f-5276061ba539
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _acmdln, _tcmdln, _wcmdln
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

内部 CRT グローバル変数。  コマンド ライン。  
  
## 構文  
  
```  
char * _acmdln; wchar_t * _wcmdln;  #ifdef WPRFLAG    #define _tcmdln _wcmdln #else    #define _tcmdln _acmdln  
```  
  
## 解説  
 これらの CRT 内部変数には、完全なコマンド ラインが格納されます。  これらは CRT のエクスポートされたシンボルで公開されていますが、コードでの使用が目的ではありません。  `_acmdln` には、データは文字列として格納されます。  `_wcmdln` には、データはワイド文字列として格納されます。  `_tcmdln` は、どちらが適切かに応じて `_acmdln` または `_wcmdln` として定義できます。  
  
## 参照  
 [グローバル変数](../c-runtime-library/global-variables.md)