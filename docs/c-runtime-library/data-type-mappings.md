---
title: "データ型のマップ | Microsoft Docs"
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
  - "_TXCHAR"
  - "_TUCHAR"
  - "_TINT"
  - "_TSCHAR"
  - "_TCHAR"
  - "TCHAR::H"
  - "TCHAR"
  - "_T"
  - "_TEXT"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_T 型"
  - "_TCHAR 型"
  - "_TEXT 型"
  - "_TINT 型"
  - "_TSCHAR 型"
  - "_TUCHAR 型"
  - "_TXCHAR 型"
  - "汎用テキストのデータ型"
  - "T 型"
  - "TCHAR 型"
  - "TCHAR.H データ型, マップ (定義済みの)"
  - "TEXT 型"
  - "TINT 型"
  - "TSCHAR 型"
  - "TUCHAR 型"
  - "TXCHAR 型"
ms.assetid: 4e573c05-8800-468b-ae5f-76ff7409835e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# データ型のマップ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのデータ型のマッピングは TCHAR.H で定義され、定数 `_UNICODE` または `_MBCS` がプログラム内で定義されているかどうかによって異なります。  
  
 関連情報については、[\_MBCS コードの TCHAR.H のデータ型を使用します。](../text/using-tchar-h-data-types-with-mbcs-code.md)を参照してください。  
  
### 汎用テキストのデータ型のマップ  
  
|汎用テキスト<br /><br /> データ型名|SBCS \(\_UNICODE、<br /><br /> \_MBCS がない<br /><br /> 定義\)|\_MBCS<br /><br /> が定義されている場合|\_UNICODE<br /><br /> が定義されている場合|  
|----------------------|-----------------------------------------------|---------------------------|------------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_tfinddata_t`|`_finddata_t`|`_finddata_t`|`_wfinddata_t`|  
|`_tfinddata64_t`|`__finddata64_t`|`__finddata64_t`|`__wfinddata64_t`|  
|`_tfinddatai64_t`|`_finddatai64_t`|`_finddatai64_t`|`_wfinddatai64_t`|  
|`_TINT`|`int`|`int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` または `_TEXT`|影響なし \(プリプロセッサによって削除される\)|影響なし \(プリプロセッサによって削除される\)|`L` \(文字または文字列に従っている Unicode に対応する\) への変換|  
  
## 参照  
 [汎用テキスト マップ](../c-runtime-library/generic-text-mappings.md)   
 [定数とグローバル変数のマップ](../c-runtime-library/constant-and-global-variable-mappings.md)   
 [ルーチンのマップ](../c-runtime-library/routine-mappings.md)   
 [汎用テキストのプログラム例](../c-runtime-library/a-sample-generic-text-program.md)   
 [汎用テキスト マップの使用](../c-runtime-library/using-generic-text-mappings.md)