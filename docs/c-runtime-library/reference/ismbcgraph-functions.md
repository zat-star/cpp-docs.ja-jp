---
title: "_ismbcgraph、_ismbcgraph_l、_ismbcprint、_ismbcprint_l、_ismbcpunct、_ismbcpunct_l、_ismbcblank、_ismbcblank_l、_ismbcspace、_ismbcspace_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbcpunct_l"
  - "_ismbcblank"
  - "_ismbcprint"
  - "_ismbcgraph_l"
  - "_ismbcblank_l"
  - "_ismbcpunct"
  - "_ismbcprint_l"
  - "_ismbcspace_l"
  - "_ismbcspace"
  - "_ismbcgraph"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ismbcspace"
  - "_ismbcgraph"
  - "_ismbcpunct"
  - "ismbcspace_l"
  - "ismbcgraph"
  - "_ismbcgraph_l"
  - "_ismbcprint"
  - "_ismbcspace_l"
  - "ismbcprint"
  - "ismbcgraph_l"
  - "ismbcspace"
  - "ismbcpunct"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbcgraph 関数"
  - "_ismbcgraph_l 関数"
  - "_ismbcprint 関数"
  - "_ismbcprint_l 関数"
  - "_ismbcpunct 関数"
  - "_ismbcpunct_l 関数"
  - "_ismbcspace 関数"
  - "_ismbcspace_l 関数"
  - "ismbcgraph 関数"
  - "ismbcgraph_l 関数"
  - "ismbcprint 関数"
  - "ismbcprint_l 関数"
  - "ismbcpunct 関数"
  - "ismbcpunct_l 関数"
  - "ismbcspace 関数"
  - "ismbcspace_l 関数"
ms.assetid: 8e0a5f47-ba64-4411-92a3-3c525d16e3be
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbcgraph、_ismbcgraph_l、_ismbcprint、_ismbcprint_l、_ismbcpunct、_ismbcpunct_l、_ismbcblank、_ismbcblank_l、_ismbcspace、_ismbcspace_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字がグラフィカル文字、表示文字、区切り記号、または空白文字であるかどうかを判定します。  
  
> [!IMPORTANT]
>  この API は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _ismbcgraph(  
   unsigned int c   
);  
int _ismbcgraph_l(  
   unsigned int c,  
   _locale_t locale   
);  
int _ismbcprint(  
   unsigned int c   
);  
int _ismbcprint_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcpunct(  
   unsigned int c  
);  
int _ismbcpunct_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcblank(  
   unsigned int c   
);  
int _ismbcblank_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcspace(  
   unsigned int c   
);  
int _ismbcspace_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `c`  
 判定対象の文字。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 これらの各ルーチンでは、文字がテスト条件を満たす場合に 0 以外の値が返され、テスト条件を満たさない場合に 0 が返されます。  `c` が \= \<255 およびそこに `_ismbb` 対応するルーチン \(たとえば、`_ismbcalnum` は `_ismbbalnum`に相当します\) の場合、結果は `_ismbb` 対応するルーチンの戻り値です。  
  
 `_l` サフィックスが付いているバージョンは、ロケールに依存する動作に対して渡されたロケールを、現在のロケールの代わりに使用する点を除いて、これらの関数のバージョンは同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
## 解説  
 これらの各関数は特定の条件で特定のマルチバイト文字をテストします。  
  
|ルーチン|テスト条件|コード ページ 932 の例|  
|----------|-----------|--------------------|  
|`_ismbcgraph`|グラフィック|`c` が空白 \( \) を除く ASCII またはカタカナの印刷可能な文字の 1 バイト表現である場合に限り、0 以外の値を返します。|  
|`_ismbcprint`|印刷可能|`c` が空白 \( \) を含む ASCII またはカタカナの印刷可能な文字の 1 バイト表現である場合に限り、0 以外の値を返します。|  
|`_ismbcpunct`|区切り記号|`c` が ASCII またはカタカナの区切り記号の 1 バイト表現である場合に限り、0 以外の値を返します。|  
|`_ismbcblank`|空白または水平タブ|`c` が空白文字または水平タブ文字の場合 \(`c`\=0x20 または `c`\=0x09\)、0 以外の値を返します。|  
|`_ismbcspace`|空白|`c` が空白文字の場合 \(`c`\=0x20 または 0x09\<\=`c`\<\=0x0D\)、0 以外の値を返します。|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_ismbcgraph`|\<mbstring.h\>|  
|`_ismbcgraph_l`|\<mbstring.h\>|  
|`_ismbcprint`|\<mbstring.h\>|  
|`_ismbcprint_l`|\<mbstring.h\>|  
|`_ismbcpunct`|\<mbstring.h\>|  
|`_ismbcpunct_l`|\<mbstring.h\>|  
|`_ismbcblank`|\<mbstring.h\>|  
|`_ismbcblank_l`|\<mbstring.h\>|  
|`_ismbcspace`|\<mbstring.h\>|  
|`_ismbcspace_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 同等の .NET Framework 関数  
  
-   [System::Char::IsPunctuation](https://msdn.microsoft.com/en-us/library/system.char.ispunctuation.aspx)  
  
-   [System::Char::IsWhiteSpace](https://msdn.microsoft.com/en-us/library/system.char.iswhitespace.aspx)  
  
-   `_ismbcgraph` および `_ismbcprint` の場合: 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_ismbc 系ルーチン](../../c-runtime-library/ismbc-routines.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)