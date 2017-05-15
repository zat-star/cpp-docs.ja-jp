---
title: mbsrtowcs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- mbsrtowcs
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
- mbsrtowcs
dev_langs:
- C++
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
caps.latest.revision: 20
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
ms.openlocfilehash: bec54ca0efe0f8aefabbe0c616e283b64fd22166
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="mbsrtowcs"></a>mbsrtowcs
現在のロケールのマルチバイト文字列を、対応するワイド文字の文字列に変換します。マルチバイト文字の途中から再開することが可能です。 この関数のセキュリティが強化されたバージョンについては、「[mbsrtowcs_s](../../c-runtime-library/reference/mbsrtowcs-s.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
size_t mbsrtowcs(  
   wchar_t *wcstr,  
   const char **mbstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t mbsrtowcs(  
   wchar_t (&wcstr)[size],  
   const char **mbstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `wcstr`  
 結果として変換されたワイド文字の文字列を格納するアドレス。  
  
 [入力、出力] `mbstr`  
 変換するマルチバイト文字列の場所への間接ポインター。  
  
 [入力] `count`  
 変換して `wcstr` に格納する最大文字数 (バイト数ではない)。  
  
 [入力、出力] `mbstate`  
 `mbstate_t` 変換状態オブジェクトへのポインター。 この値が null ポインターの場合、静的な内部変換状態オブジェクトが使用されます。 内部 `mbstate_t` オブジェクトはスレッド セーフではないため、常に独自の `mbstate` パラメーターを渡すことをお勧めします。  
  
## <a name="return-value"></a>戻り値  
 正常に変換された文字数を返します (終端の null 文字があっても含まれません)。 エラーが発生した場合に (size_t)(-1) を返し、`errno` を EILSEQ に設定します。  
  
## <a name="remarks"></a>コメント  
 `mbsrtowcs` 関数は、`mbstr` が間接的に指すマルチバイト文字列を、`wcstr` に含まれる変換状態を使用して、`mbstate` が指すバッファーに格納されるワイド文字に変換します。 終端 null マルチバイト文字が検出されるまで、あるいは現在のロケールの有効な文字に対応しないマルチバイト シーケンスが検出されるか、`count` 文字分の変換が済むまで、各文字が変換されていきます。 `mbsrtowcs` は、`count` の発生前または発生時にマルチバイト null 文字 ('\0') を検出すると、それを 16 ビットの終端 null 文字に変換して停止します。  
  
 このため、`wcstr` のワイド文字の文字列が null 終了になるのは、`mbsrtowcs` が変換中にマルチバイト null 文字を検出した場合だけです。 `mbstr` および `wcstr` が指すシーケンスが重なり合う場合、`mbsrtowcs` の動作は未定義です。 `mbsrtowcs` は、現在のロケールの LC_TYPE カテゴリの影響を受けます。  
  
 `mbsrtowcs` 関数は、再開できるという点で [mbstowcs_s、_mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md) と異なります。 同じ関数または再開可能な他の関数の後続の呼び出しのために、変換状態が `mbstate` に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。  たとえば、`mbsrlen` の代わりに `mbslen` の後続の呼び出しが使用されている場合、アプリケーションは `mbsrtowcs` の代わりに `mbstowcs.` を使用する必要があります。  
  
 `wcstr` が null ポインターでない場合、`mbstr` が指すポインター オブジェクトは、終端の null 文字に達したために変換が停止したときに null ポインターが割り当てられます。 それ以外の場合、変換された最後のマルチバイト文字がある場合は、その後ろのアドレスが割り当てられます。 これにより、後続の関数呼び出しで、この呼び出しが停止した場所から変換を再開できます。  
  
 `wcstr` 引数が null ポインターの場合、`count` 引数は無視され、`mbsrtowcs` は変換先の文字列に必要なサイズをワイド文字数で返します。 `mbstate` が null ポインターの場合、関数はスレッド セーフではない静的な `mbstate_t` 内部変換状態オブジェクトを使用します。 文字シーケンス `mbstr` に対応するマルチバイト文字の表現がない場合、-1 が返され、`errno` が `EILSEQ` に設定されます。  
  
 `mbstr` が null ポインターである場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、-1 を返します。  
  
 C++ では、この関数にテンプレートのオーバーロードがあります。このオーバーロードは、この関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
## <a name="exceptions"></a>例外  
 `mbsrtowcs` 関数は、この関数の実行中に現行スレッドのどの関数も `setlocale` を呼び出さず、かつ `mbstate` 引数が null ポインターでない限り、マルチスレッド セーフです。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`mbsrtowcs`|\<wchar.h>|  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [mbstowcs、_mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)
