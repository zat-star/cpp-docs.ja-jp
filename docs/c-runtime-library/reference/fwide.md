---
title: "fwide | Microsoft Docs"
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
  - "fwide"
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
  - "fwide"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fwide 関数"
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fwide
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

実装されていない。  
  
## 構文  
  
```  
int fwide(  
   FILE *stream,  
   int mode;  
);  
```  
  
#### パラメーター  
 `stream`  
 `FILE` 構造体へのポインター \(無視されます\)。  
  
 `mode`  
 ストリームの新しい幅: ワイド文字は、バイトの負の正そのまま残しておくため。\(この値は無視されます。  
  
## 戻り値  
 この関数は、現在 `mode`を返します。  
  
## 解説  
 この関数の現在のバージョンが標準に従いません。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`fwide`|\<wchar.h\>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。