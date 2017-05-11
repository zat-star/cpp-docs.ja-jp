---
title: "_cgets_s、_cgetws_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _cgetws_s
- _cgets_s
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cgets_s
- cgets_s
- cgetws_s
- _cgetws_s
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], getting from console
- console, getting strings from
- _cgets_s function
- cget_s function
- _cgetws_s function
- cgetws_s function
ms.assetid: 38b74897-afe6-4dd9-a43f-36a3c0d72c5c
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: cad572e3b312ad29878486c9f40dafc2e96917f9
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="cgetss-cgetwss"></a>_cgets_s、_cgetws_s
コンソールから文字列を取得します。 これらのバージョンの [_cgets および _cgetws](../../c-runtime-library/cgets-cgetws.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンです。  
  
> [!IMPORTANT]
>  この API は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _cgets_s(   
   char *buffer,  
   size_t numberOfElements,  
   size_t *pSizeRead  
);  
errno_t _cgetws_s(  
   wchar_t *buffer  
   size_t numberOfElements,  
   size_t *pSizeRead  
);  
template <size_t size>  
errno_t _cgets_s(   
   char (&buffer)[size],  
   size_t *pSizeRead  
); // C++ only  
template <size_t size>  
errno_t _cgetws_s(  
   wchar_t (&buffer)[size],  
   size_t *pSizeRead  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `buffer`  
 データの格納場所。  
  
 [入力] `numberOfElements`  
 バッファーのサイズです。単位はバイト数またワイド文字数です。これは、読み取る最大の文字数でもあります。  
  
 [入力] `pSizeRead`  
 実際に読み取った文字数。  
  
## <a name="return-value"></a>戻り値  
 成功した場合の戻り値は 0 です。それ以外の場合 (エラー発生時) は、エラー コードです。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`buffer`|`numberOfElements`|`pSizeRead`|リターン|`buffer` の内容|  
|--------------|------------------------|-----------------|------------|--------------------------|  
|`NULL`|任意|任意|`EINVAL`|適用なし|  
|`NULL` 以外|ゼロ|任意|`EINVAL`|変更されない|  
|`NULL` 以外|任意|`NULL`|`EINVAL`|長さゼロの文字列|  
  
## <a name="remarks"></a>コメント  
 `_cgets_s` および `_cgetws_s` は、コンソールから文字列を読み取り、その文字列 (null で終了する) を `buffer` にコピーします。 `_cgetws_s` はこの関数のワイド文字バージョンで、文字のサイズを除いて、これら 2 つの関数の動作は同じです。 読み取る文字列の最大サイズは、`numberOfElements` パラメーターに入れて渡します。 このサイズには、終端の null に対応する追加の文字を含める必要があります。 実際に読み取られた文字数は、`pSizeRead` に置かれます。  
  
 操作中に、またはパラメーターを検証する際にエラーが発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」の説明にあるとおり無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`errno` が `EINVAL` に設定され、`EINVAL` が返されます。  
  
 C++ では、テンプレートのオーバーロードを利用すると、これらの関数の使用が簡素化されます。オーバーロードでは、バッファー長が自動的に推論されるのでサイズ引数を指定する必要がなくなるだけでなく、古くてセキュリティが万全ではない関数を新しくてセキュリティが強化された関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_cgetts_s`|`_cgets_s`|`_cgets_s`|`_cgetws_s`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_cgets_s`|\<conio.h>|  
|`_cgetws_s`|\<conio.h> または \<wchar.h>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンソール入出力とポート入出力](../../c-runtime-library/console-and-port-i-o.md)   
 [_getch、_getwch](../../c-runtime-library/reference/getch-getwch.md)
