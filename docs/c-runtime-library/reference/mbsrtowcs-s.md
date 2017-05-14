---
title: mbsrtowcs_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- mbsrtowcs_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsrtowcs_s
dev_langs:
- C++
helpviewer_keywords:
- mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
caps.latest.revision: 24
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
ms.openlocfilehash: 920af1d0e06c7af71c3a98bf07f451f4d50f2659
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="mbsrtowcss"></a>mbsrtowcs_s
現在のロケールのマルチバイト文字の文字列をワイド文字の文字列表現に変換します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおりセキュリティーが強化されたバージョンの [mbsrtowcs](../../c-runtime-library/reference/mbsrtowcs.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t mbsrtowcs_s(  
   size_t * pReturnValue,  
   wchar_t * wcstr,  
   size_t sizeInWords,  
   const char ** mbstr,  
   size_t count,  
   mbstate_t * mbstate  
);  
template <size_t size>  
errno_t mbsrtowcs_s(  
   size_t * pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char ** mbstr,  
   size_t count,  
   mbstate_t * mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `pReturnValue`  
 変換された文字数。  
  
 [出力] `wcstr`  
 結果として変換されたワイド文字の文字列を格納するバッファーのアドレス。  
  
 [出力] `sizeInWords`  
 `wcstr` のワードでのサイズ (ワイド文字)。  
  
 [入力、出力] `mbstr`  
 変換されるマルチバイト文字の文字列の場所への間接ポインター。  
  
 [入力] `count`  
 `wcstr` バッファーに格納するワイド文字の最大数 (終端の null を含みません) か、[_TRUNCATE](../../c-runtime-library/truncate.md)。  
  
 [入力、出力] `mbstate`  
 `mbstate_t` 変換状態オブジェクトへのポインター。 この値が null ポインターの場合、静的な内部変換状態オブジェクトが使用されます。 内部 `mbstate_t` オブジェクトはスレッド セーフではないため、常に独自の `mbstate` パラメーターを渡すことをお勧めします。  
  
## <a name="return-value"></a>戻り値  
 変換が正常に終了した場合は 0 を返し、失敗した場合はエラー コードを返します。  
  
|エラー条件|戻り値および `errno`|  
|---------------------|------------------------------|  
|`wcstr` が null ポインター、かつ `sizeInWords` > 0|`EINVAL`|  
|`mbstr` が null ポインター|`EINVAL`|  
|
          `mbstr` が間接的に指している文字列には、現在のロケールで無効なマルチバイト シーケンスが含まれています。|`EILSEQ`|  
|コピー先のバッファーが小さすぎて変換後の文字列を含めることができません (`count` が `_TRUNCATE` の場合を除きます。詳細については、「解説」を参照してください。)。|`ERANGE`|  
  
 これらのいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているとおり無効なパラメーター例外が呼び出されます。 実行の続行が許可された場合、関数はエラー コードを返し、表に示すように `errno` を設定します。  
  
## <a name="remarks"></a>コメント  
 `mbsrtowcs_s` 関数は、`mbstr` が間接的に指すマルチバイト文字列を、`wcstr` に含まれる変換状態を使用して、`mbstate` が指すバッファーに格納されるワイド文字に変換します。 これらの条件のいずれかが満たされるまで、各文字に対して変換が続きます。  
  
-   マルチバイトの null 文字が検出されました。  
  
-   無効なマルチバイト文字が検出されました。  
  
-   `wcstr` バッファーに格納されているワイド文字の数が `count` と同じです。  
  
 変換先の文字列 `wcstr` は、エラーの場合でも常に null で終わります。ただし、`wcstr` が null ポインターの場合を除きます。  
  
 `count` が特殊値 [_TRUNCATE](../../c-runtime-library/truncate.md) の場合、`mbsrtowcs_s` は null 終端文字用の空きを残して、コピー先のバッファーに収まる限りの文字列に変換されます。  
  
 `mbsrtowcs_s` は、元の文字列を正常に変換すると、変換後の文字列のワイド文字と null 終端文字のサイズを `*``pReturnValue` に書き込みます (`pReturnValue` が Null ポインターでない場合に限ります)。 これは、`wcstr` 引数が null ポインターであり、必要なバッファー サイズを決定できる場合でも発生します。 `wcstr` が null ポインターの場合、`count` は無視されます。  
  
 `wcstr` が null ポインターでない場合、`mbstr` が指すポインター オブジェクトは、終端の null 文字に達したために変換が停止したときに null ポインターが割り当てられます。 それ以外の場合、変換された最後のマルチバイト文字がある場合は、その後ろのアドレスが割り当てられます。 これにより、後続の関数呼び出しで、この呼び出しが停止した場所から変換を再開できます。  
  
 `mbstate` が null ポインターの場合、ライブラリの内部 `mbstate_t` 変換状態の静的オブジェクトが使用されます。 この内部静的オブジェクトはスレッド セーフではないため、常に独自の `mbstate` の値を渡すことをお勧めします。  
  
 `mbsrtowcs_s` は、現在のロケールで有効ではないマルチバイト文字が検出された場合、`*``pReturnValue` に -1 を入れ、コピー先バッファー `wcstr` を空文字列に設定し、`errno` を `EILSEQ` に設定して、`EILSEQ` を返します。  
  
 `mbstr` および `wcstr` が指すシーケンスが重なり合う場合、`mbsrtowcs_s` の動作は未定義です。 `mbsrtowcs_s` は、現在のロケールの LC_TYPE カテゴリの影響を受けます。  
  
> [!IMPORTANT]
>  `wcstr` と `mbstr` が重なり合わず、変換するマルチバイト文字の数が `count` に適切に反映されていることを確認します。  
  
 `mbsrtowcs_s` 関数は、再開できるかどうかの点で [mbstowcs_s、_mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md) と異なります。 同じ関数または再開可能な他の関数の後続の呼び出しのために、変換状態が `mbstate` に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、`mbsrlen` の代わりに `mbslen` の後続の呼び出しが使用されている場合、アプリケーションは `mbsrtowcs_s` の代わりに `mbstowcs_s.` を使用する必要があります。  
  
 C++ では、この関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
## <a name="exceptions"></a>例外  
 `mbsrtowcs_s` 関数は、この関数の実行中ずっと現行スレッドのどの関数も `setlocale` を呼び出さず、かつ `mbstate` 引数が null ポインターでない限り、マルチスレッド セーフです。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`mbsrtowcs_s`|\<wchar.h>|  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [mbstowcs_s、_mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)
