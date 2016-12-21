---
title: "_free_locale | Microsoft Docs"
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
  - "_free_locale"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__free_locale"
  - "free_locale"
  - "_free_locale"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__free_locale 関数"
  - "_free_locale 関数"
  - "free_locale 関数"
  - "ロケール, 解放"
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _free_locale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ロケール オブジェクトを解放します。  
  
## 構文  
  
```  
void _free_locale(  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `locale`  
 入力解放するロケール オブジェクト。  
  
## 解説  
 `_free_locale` 関数を呼び出し、解放するので `_get_current_locale` または `_create_locale`するロケール オブジェクトを使用します。  
  
 この関数は、`__free_locale` の以前の名前 \(2 個の先頭にアンダースコアが\) は推奨されていません。  
  
## 必要条件  
  
|`Routine`|必須ヘッダー|  
|---------------|------------|  
|`_free_locale`|\<locale.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 対応する項目はありません。  
  
## 参照  
 [\_get\_current\_locale](../Topic/_get_current_locale.md)   
 [\_create\_locale、\_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)