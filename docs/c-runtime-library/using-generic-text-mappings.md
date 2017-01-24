---
title: "汎用テキスト マップの使用 | Microsoft Docs"
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
  - "_UNICODE"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_MBCS データ型"
  - "_T 型"
  - "_TCHAR 型"
  - "_TEXT 型"
  - "_TINT 型"
  - "_TSCHAR 型"
  - "_TUCHAR 型"
  - "_TXCHAR 型"
  - "_UNICODE 定数"
  - "汎用テキストのデータ型"
  - "汎用テキスト マップ"
  - "マップ, 汎用テキスト"
  - "MBCS データ型"
  - "T 型"
  - "TCHAR 型"
  - "TCHAR.H データ型, マップ (定義済みの)"
  - "TEXT 型"
  - "TINT 型"
  - "TSCHAR 型"
  - "TUCHAR 型"
  - "TXCHAR 型"
  - "UNICODE 定数"
ms.assetid: 2848121c-e51f-4b9b-a2e6-833ece4b0cb3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 汎用テキスト マップの使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 さまざまな国際市場向けのコード開発を単純化するために、Microsoft ランタイム ライブラリには、多くのデータ型、ルーチン、およびそのほかのオブジェクトに Microsoft 固有の「汎用テキスト マップ」を提供します。  これらの割り当ては TCHAR.H.で定義されます。  文字セットの 3 種類のいずれかにコンパイルできるジェネリック コードを記述するために、これらの名前のマッピングを使用する: SBCS ASCII \(\)、マニフェスト定数に、MBCS、Unicode、`#define` のステートメントを使用して定義します。  汎用テキスト マッピングは ANSI 互換の Microsoft 拡張機能です。  
  
### 汎用テキスト マッピング用のプリプロセッサ ディレクティブ  
  
|\#define|コンパイル後の状態|例|  
|--------------|---------------|-------|  
|`_UNICODE`|Unicode \(ワイド文字\)|`_tcsrev` は `_wcsrev` に割り当てられます。|  
|`_MBCS`|マルチバイト文字|`_tcsrev` は `_mbsrev` に割り当てられます。|  
|なし \(既定: `_UNICODE` が `_MBCS` が定義されていません\)|SBCS ASCII \(\)|`strrev`への`_tcsrev`のマップ|  
  
 たとえば `_UNICODE`が定義されている `MBCS` がプログラム内で定義されている場合は `_wcsrev`マップします TCHAR.H で定義された汎用テキスト関数 `_tcsrev`に `mbsrev` に。  `strrev`にそれ `_tcsrev`の対応マップです。  
  
 これらの定数を定義する `_UNICODE` が入力を定義すると、`char` をマップします `_MBCS` が定義されている場合、TCHAR.H で定義された汎用テキスト データ型 `_TCHAR`は、`wchar_t` を入力するに `char` を入力する。  他のデータ型のマッピングは、プログラミングの便宜上 TCHAR.H で提供されますが、`_TCHAR` は最も有用な型です。  
  
### 汎用テキストのデータ型のマップ  
  
|汎用テキスト データ型名|SBCS \(定義されていない\_UNICODE、\_MBCS\)|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|------------------|---------------------------------------|-----------------------|--------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_TINT`|`int`|`int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` または `_TEXT`|影響なし \(プリプロセッサによって削除される\)|影響なし \(プリプロセッサによって削除される\)|`L` \(文字または文字列に従っている Unicode に対応する\) への変換|  
  
 汎用テキスト ルーチンのマップの一覧については、変数、そのほかのオブジェクトは、[汎用テキストのマッピング](../c-runtime-library/generic-text-mappings.md)を参照します。  
  
 次のコードは、MBCS、および Unicode SBCS モデルに対応するために、`_TCHAR` と `_tcsrev` の使用例です。  
  
```  
_TCHAR *RetVal, *szString;  
RetVal = _tcsrev(szString);  
```  
  
 `MBCS` が定義されていると、プリプロセッサによって次のコードには、フラグメントをマップします:  
  
```  
char *RetVal, *szString;  
RetVal = _mbsrev(szString);  
```  
  
 `_UNICODE` が定義されていると、プリプロセッサによって次のコードに同じフラグメントをマップします:  
  
```  
wchar_t *RetVal, *szString;  
RetVal = _wcsrev(szString);  
```  
  
 `_MBCS` が `_UNICODE` も定義されていない場合、プリプロセッサは前 ASCII コードを次のように、フラグメントをマップします:  
  
```  
char *RetVal, *szString;  
RetVal = strrev(szString);  
```  
  
 したがって、単一のソース・コード ファイルの記述と保守を、文字セットの 3 種類のいずれかに固有のルーチンを実行するようにコンパイルできます。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [汎用テキスト マップ](../c-runtime-library/generic-text-mappings.md)   
 [データ型のマップ](../c-runtime-library/data-type-mappings.md)   
 [定数とグローバル変数のマップ](../c-runtime-library/constant-and-global-variable-mappings.md)   
 [ルーチンのマップ](../c-runtime-library/routine-mappings.md)   
 [汎用テキストのプログラム例](../c-runtime-library/a-sample-generic-text-program.md)