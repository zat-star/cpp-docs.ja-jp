---
title: "offsetof マクロ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
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
  - "offsetof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "offsetof マクロ"
  - "構造体メンバー, オフセット"
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# offsetof マクロ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

親構造体の先頭からメンバーのオフセットを取得します。  
  
## 構文  
  
```  
  
        size_t offsetof(  
   structName,  
   memberName   
);  
```  
  
#### パラメーター  
 *structName*  
 親データ構造体の名前。  
  
 `memberName`  
 オフセットを決定する親データ構造体のメンバーの名前。  
  
## 戻り値  
 `offsetof` は、親データ構造体の先頭から、指定されたメンバーのオフセットをバイト単位で返します。  ビット フィールドには定義されません。  
  
## 解説  
 `offsetof` マクロは、*structName* によって指定された構造体の先頭からバイト単位で数えた `memberName` のオフセットを、`size_t` 型の値として返します。  `struct` キーワードで型を指定できます。  
  
> [!NOTE]
>  `offsetof` は関数ではないため、C のプロトタイプを使用して記述することはできません。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`offsetof`|\< stddef.h \>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)