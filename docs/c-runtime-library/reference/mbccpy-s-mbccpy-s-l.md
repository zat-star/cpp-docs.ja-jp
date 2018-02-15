---
title: "_mbccpy_s、_mbccpy_s_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mbccpy_s
- _mbccpy_s_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbccpy_s_l
- mbccpy_s_l
- mbccpy_s
- _mbccpy_s
dev_langs:
- C++
helpviewer_keywords:
- tccpy_s_l function
- _tccpy_s function
- _mbccpy_s function
- mbccpy_s function
- tccpy_s function
- mbccpy_s_l function
- _tccpy_s_l function
- _mbccpy_s_l function
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 72b2e155dafe0b5fb5a83e5e62ea95fd2c3657e6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="mbccpys-mbccpysl"></a>_mbccpy_s、_mbccpy_s_l
文字列のマルチバイト文字 1 個を他の文字列にコピーします。 これらのバージョンの [_mbccpy、_mbccpy_l](../../c-runtime-library/reference/mbccpy-mbccpy-l.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」で説明されているように、セキュリティが強化されています。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、次を参照してください。[ユニバーサル Windows プラットフォーム アプリでサポートされない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _mbccpy_s(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src   
);  
errno_t _mbccpy_s_l(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
);  
template <size_t size>  
errno_t _mbccpy_s(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src   
); // C++ only  
template <size_t size>  
errno_t _mbccpy_s_l(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `dest`  
 コピー先。  
  
 [入力] `buffSizeInBytes`  
 コピー先のバッファーのサイズ。  
  
 [出力] `pCopied`  
 コピーされたバイト数が格納されます (正常終了した場合は 1 または 2)。 バイト数を考慮しない場合は、`NULL` を渡します。  
  
 [入力] `src`  
 コピーするマルチバイト文字。  
  
 [入力] `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。 `src` または `dest` が `NULL` の場合、あるいは `buffSizeinBytes` の値を超えるバイト数を `dest` にコピーしようとした場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、関数は `EINVAL` を返し、`errno` が `EINVAL` に設定されます。  
  
## <a name="remarks"></a>コメント  
 `_mbccpy_s` 関数は、`src` から `dest` に、マルチバイト文字を 1 文字コピーします。 [_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md) への暗黙の呼び出しによって、`src` がマルチバイト文字の先行バイトを指していないと判断された場合、`src` が指している 1 バイトがコピーされます。 `src` が先行バイトを指しているが、後続のバイトが 0 であるため無効となる場合は、`dest` に 0 がコピーされ、`errno` が `EILSEQ` に設定されて、関数から `EILSEQ` が返されます。  
  
 `_mbccpy_s` 関数は null 終端文字を追加しません。ただし、`src` が null 文字を指している場合は、その null が `dest` にコピーされます (単なる通常の 1 バイトのコピー)。  
  
 `pCopied` の値には、コピーされたバイト数が格納されます。 操作が正常に終了した場合は、1 と 2 のどちらかの値となります。 `NULL` が渡されると、このパラメーターは無視されます。  
  
|`src`|`dest` へのコピー対象|`pCopied`|戻り値|  
|-----------|----------------------|---------------|------------------|  
|先行バイト以外|先行バイト以外|1|0|  
|0|0|1|0|  
|後続が 0 以外の先行バイト|後続が 0 以外の先行バイト|2|0|  
|後続が 0 以外の先行バイト|0|1|`EILSEQ`|  
  
 2 行目は、単に 1 行目の特殊なケースです。 また、この表では `buffSizeInBytes` >= `pCopied` を前提としています。  
  
 `_mbccpy_s` は、すべてのロケールに依存する動作に現在のロケールを使用します。 `_mbccpy_s_l` は `_mbccpy_s` と同じですが、`_mbccpy_s_l` は現在のロケールではなく渡されたロケールを使用するという点で異なります。  
  
 C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tccpy_s`|マクロまたはインライン関数に割り当てる。|`_mbccpy_s`|マクロまたはインライン関数に割り当てる。|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_mbccpy_s`|\<mbstring.h>|  
|`_mbccpy_s_l`|\<mbstring.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen、mblen、_mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)