---
title: "ATL テキスト エンコード関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ae1648b-2b87-4112-92aa-0069fcfd23da
caps.latest.revision: 3
translationtype: Machine Translation
ms.sourcegitcommit: 9ab4b38b2ba14aca2240d12fff966d36750a3229
ms.openlocfilehash: 86433bebe3fe84a027d7725525e028d80b67e358
ms.lasthandoff: 02/24/2017

---
# <a name="atl-text-encoding-functions"></a>ATL テキスト エンコード関数
これらの関数は、テキスト エンコードおよびデコードをサポートします。

|||  
|-|-|  
|[AtlGetHexValue](#atlgethexvalue)|16 進数の数値を取得します。|   
|[AtlGetVersion](#atlgetversion)|使用する、ATL ライブラリのバージョンを取得するには、この関数を呼び出します。  |  
|[AtlHexDecode](#atlhexdecode)|以前の呼び出しで&16; 進テキストとしてエンコードされているデータの文字列をデコード[AtlHexEncode](#atlhexencode)します。|
|[AtlHexDecodeGetRequiredLength](#atlhexdecodegetrequiredlength)|指定した長さの&16; 進エンコードされた文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。|
|[AtlHexEncode](#atlhexencode)|一部のデータを&16; 進テキストの文字列としてエンコードします。|
|[AtlHexEncodeGetRequiredLength](#atlhexencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|
|[AtlHexValue](#atlhexvalue)|16 進数の数値を取得します。 |
|[AtlUnicodeToUTF8](#atlunicodetoutf8)|Unicode 文字列を UTF-8 に変換します。 |
|[BEncode](#bencode)|"B" エンコーディングを使用して一部のデータを変換します。|
|[BEncodeGetRequiredLength](#beencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|
|[EscapeXML](#escapexml)|XML での使用には安全でない文字を安全な文字に変換します。|
|[GetExtendedChars](#getextendedchars)|文字列に含まれる拡張文字の数を取得します。|
|[IsExtendedChar](#isextendedchar)|指定された文字が拡張文字 (文字コードが 31 以下または 127 以上で、タブ、ラインフィード、キャリッジ リターン以外の文字) かどうかを判断します。|
|[QEncode](#qencode)|"Q" エンコーディングを使用して一部のデータを変換します。  |
|[QEncodeGetRequiredLength](#qencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|
|[QPDecode](#qpdecode)|前の呼び出しによってなど quoted-printable 形式にエンコードされたデータの文字列をデコード[QPEncode](#qpencode)します。|
|[QPDecodeGetRequiredLength](#qpdecodegetrequiredlength)|quoted-printable にエンコードされた指定長の文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。|
|[QPEncode](#qpencode)|一部のデータを quoted-printable 形式にエンコードします。|
|[QPEncodeGetRequiredLength](#qpencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|
|[UUDecode](#uudecode)|などを以前の呼び出しによって uuencode されているデータの文字列をデコード[UUEncode](#uuencode)します。|
|[UUDecodeGetRequiredLength](#uudecodegetrequiredlength)|指定した長さの uuencode された文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。|
|[UUEncode](#uuencode)|データを uuencode します。 |
|[UUEncodeGetRequiredLength](#uuencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|

## <a name="requirements"></a>要件  
 **ヘッダー:** atlenc.h  
 
## <a name="a-nameatlgethexvaluea-atlgethexvalue"></a><a name="atlgethexvalue"></a>AtlGetHexValue
16 進数の数値を取得します。  
  
```    
inline char AtlGetHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `chIn`  
 16 進文字 '0' ~ '9'、'A'-'F' または 'a'-'f' です。  
  
### <a name="return-value"></a>戻り値  
 入力文字の数値は、16 進数として解釈されます。 たとえば、'0' の入力には、値 0 が返されます、'A' の入力が 10 の値を返します。 入力文字が&16; 進数字でない場合は、この関数は-1 を返します。  
  
## <a name="a-nameatlgetversiona-atlgetversion"></a><a name="atlgetversion"></a>AtlGetVersion
使用する、ATL ライブラリのバージョンを取得するには、この関数を呼び出します。  
  
```  
ATLAPI_(DWORD) AtlGetVersion(void* pReserved);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pReserved`  
 予約済みのポインター。  
  
### <a name="return-value"></a>戻り値  
 返します。、`DWORD`コンパイルまたは実行されている、ATL ライブラリのバージョンの整数値。  
  
## <a name="example"></a>例  
 次のように、関数を呼び出す必要があります。  
  
 [!code-cpp[NVC_ATL_Utilities #&95;](../../atl/codesnippet/cpp/atl-text-encoding-functions_1.cpp)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  

## <a name="a-nameatlhexdecodea-atlhexdecode"></a><a name="atlhexdecode"></a>AtlHexDecode
以前の呼び出しで&16; 進テキストとしてエンコードされているデータの文字列をデコード[AtlHexEncode](#atlhexencode)します。  
  
```    
inline BOOL AtlHexDecode(  
   LPCSTR pSrcData,  
   int nSrcLen,  
   LPBYTE pbDest,  
   int* pnDestLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `pSrcData`  
 デコードするデータを含む文字列です。  
  
 `nSrcLen`  
 文字の長さ`pSrcData`です。  
  
 `pbDest`  
 デコードされたデータを受信する呼び出し元が割り当てたバッファーです。  
  
 `pnDestLen`  
 バイトの長さを格納する変数を指すポインター`pbDest`します。 関数が成功した場合、変数は、バッファーに書き込まれたバイト数を受け取ります。 関数が失敗した場合、変数は、バッファーのバイト単位で、必要な長さを受信します。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
## <a name="a-nameatlhexdecodegetrequiredlengtha-atlhexdecodegetrequiredlength"></a><a name="atlhexdecodegetrequiredlength"></a>AtlHexDecodeGetRequiredLength
指定した長さの&16; 進エンコードされた文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。  
  
```  
inline int AtlHexDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードされた文字列内の文字の数。  
  
### <a name="return-value"></a>戻り値  
 デコードされた文字列を格納するバッファーの必要なバイト数`nSrcLen`文字です。  
  
## <a name="a-nameatlhexencodea-atlhexencode"></a><a name="atlhexencode"></a>AtlHexEncode
一部のデータを&16; 進テキストの文字列としてエンコードします。  
  
```  
inline BOOL AtlHexEncode(  
   const BYTE * pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
int * pnDestLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `pbSrcData`  
 エンコードするデータを保持するバッファー。  
  
 `nSrcLen`  
 エンコードするデータの長さを (バイト単位)。  
  
 `szDest`  
 エンコードされたデータを受信する呼び出し元が割り当てたバッファーです。  
  
 `pnDestLen`  
 文字の長さを格納する変数へのポインター`szDest`します。 関数が成功した場合、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 ソース データの各バイトは、2 つの 16 進文字とエンコードされます。  
  
## <a name="a-nameatlhexencodegetrequiredlengtha-atlhexencodegetrequiredlength"></a><a name="atlhexencodegetrequiredlength"></a>AtlHexEncodeGetRequiredLength
指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。  
  
```  
inline int AtlHexEncodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードするデータのバイト数。  
  
### <a name="return-value"></a>戻り値  
 文字のエンコードされたデータを格納するバッファーに必要な数`nSrcLen`バイトです。  
  
## <a name="a-nameatlhexvaluea-atlhexvalue"></a><a name="atlhexvalue"></a>AtlHexValue
16 進数の数値を取得します。  
  
```  
inline short AtlHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `chIn`  
 16 進文字 '0' ~ '9'、'A'-'F' または 'a'-'f' です。  
  
### <a name="return-value"></a>戻り値  
 入力文字の数値は、16 進数として解釈されます。 たとえば、'0' の入力には、値 0 が返されます、'A' の入力が 10 の値を返します。 入力文字が&16; 進数字でない場合は、この関数は-1 を返します。  
  
## <a name="a-nameatlunicodetoutf8a-atlunicodetoutf8"></a><a name="atlunicodetoutf8"></a>AtlUnicodeToUTF8
Unicode 文字列を UTF-8 に変換します。  
  
```  
ATL_NOINLINE inline int AtlUnicodeToUTF8(  
   LPCWSTR wszSrc,  
   int nSrc,  
   LPSTR szDest,  
   int nDest) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *wszSrc*  
 変換する Unicode 文字列  
  
 `nSrc`  
 Unicode 文字列の文字数。  
  
 `szDest`  
 変換後の文字列を受け取る呼び出し元が割り当てたバッファーです。  
  
 `nDest`  
 バッファーの長さをバイト単位です。  
  
### <a name="return-value"></a>戻り値  
 変換後の文字列の文字数を返します。  
  
### <a name="remarks"></a>コメント  
 変換後の文字列に必要なバッファーのサイズを決定するには、0 を渡すことこの関数を呼び出す`szDest`と`nDest`です。  
  
## <a name="a-namebencodea-bencode"></a><a name="bencode"></a>BEncode  
"B" エンコーディングを使用して一部のデータを変換します。  
  
```  
inline BOOL BEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCSTR pszCharSet) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `pbSrcData`  
 エンコードするデータを保持するバッファー。  
  
 `nSrcLen`  
 エンコードするデータの長さを (バイト単位)。  
  
 `szDest`  
 エンコードされたデータを受信する呼び出し元が割り当てたバッファーです。  
  
 `pnDestLen`  
 文字の長さを格納する変数へのポインター`szDest`します。 関数が成功した場合、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。  
  
 `pszCharSet`  
 文字が変換を使用して設定します。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 "B"エンコーディング方式については、「RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt))。  
  
## <a name="a-namebeencodegetrequiredlengtha-bencodegetrequiredlength"></a><a name="beencodegetrequiredlength"></a>BEncodeGetRequiredLength 
指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。  
  
```  
inline int BEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードするデータのバイト数。  
  
 `nCharsetLen`  
 変換に使用する文字セットの文字数。  
  
### <a name="return-value"></a>戻り値  
 文字のエンコードされたデータを格納するバッファーに必要な数`nSrcLen`バイトです。  
  
### <a name="remarks"></a>コメント  
 "B"エンコーディング方式については、「RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt))。  
  
## <a name="a-nameescapexmla-escapexml"></a><a name="escapexml"></a>EscapeXML
XML での使用には安全でない文字を安全な文字に変換します。  
  
```  
inline int EscapeXML(  
   const wchar_t * szIn,  
   int nSrcLen,  
   wchar_t * szEsc,  
   int nDestLen,  
   DWORD dwFlags = ATL_ESC_FLAG_NONE) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `szIn`  
 変換対象の文字列。  
  
 *nSrclen*  
 変換される文字列の文字数。  
  
 *szEsc*  
 変換後の文字列を受け取る呼び出し元が割り当てたバッファーです。  
  
 *nDestLen*  
 呼び出し元が割り当てたバッファーの文字数。  
  
 `dwFlags`  
 変換を実行する方法を示すフラグ。 参照してください[ATL_ESC フラグ](http://msdn.microsoft.com/library/daf3aa3c-7498-4d63-9fb6-e05b4815c2b8)します。  
  
### <a name="return-value"></a>戻り値  
 変換後の文字列の文字数。  
  
### <a name="remarks"></a>コメント  
 テーブルには、この関数によって実行される可能性の変換を示します。  
  
|ソース|保存先|  
|------------|-----------------|  
|\<|&lt;|  
|>|&gt;|  
|&|&amp;|  
|'|&apos;|  
|"|&quot;|  
  
## <a name="a-namegetextendedcharsa-getextendedchars"></a><a name="getextendedchars"></a>GetExtendedChars
文字列に含まれる拡張文字の数を取得します。  
  
```  
inline int GetExtendedChars(LPCSTR szSrc, int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `szSrc`  
 分析する文字列。  
  
 `nSrcLen`  
 文字列の文字の長さ。  
  
### <a name="return-value"></a>戻り値  
 によって決定される文字列内で見つかった拡張文字の数を返します[IsExtendedChar](#isextendedchar)します。  
  
## <a name="a-nameisextendedchara-isextendedchar"></a><a name="isextendedchar"></a>IsExtendedChar
指定された文字が拡張文字 (文字コードが 31 以下または 127 以上で、タブ、ラインフィード、キャリッジ リターン以外の文字) かどうかを判断します。  
  
```  
inline int IsExtendedChar(char ch) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *ch*  
 テストする文字  
  
### <a name="return-value"></a>戻り値  
 **TRUE**文字が拡張されている場合**FALSE**それ以外の場合。  
  
## <a name="a-nameqencodea-qencode"></a><a name="qencode"></a>QEncode
"Q" エンコーディングを使用して一部のデータを変換します。  
  
```  
inline BOOL QEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCSTR pszCharSet,  
   int* pnNumEncoded = NULL) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `pbSrcData`  
 エンコードするデータを保持するバッファー。  
  
 `nSrcLen`  
 エンコードするデータの長さを (バイト単位)。  
  
 `szDest`  
 エンコードされたデータを受信する呼び出し元が割り当てたバッファーです。  
  
 `pnDestLen`  
 文字の長さを格納する変数へのポインター`szDest`します。 関数が成功した場合、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。  
  
 `pszCharSet`  
 文字が変換を使用して設定します。  
  
 *pnNumEncoded*  
 変換する必要があった安全でない文字の数を格納する変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 "Q"エンコーディング方式については、「RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt))。  
  
## <a name="a-nameqencodegetrequiredlengtha-qencodegetrequiredlength"></a><a name="qencodegetrequiredlength"></a>QEncodeGetRequiredLength 
指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。  
  
```  
inline int QEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードするデータのバイト数。  
  
 `nCharsetLen`  
 変換に使用する文字セットの文字数。  
  
### <a name="return-value"></a>戻り値  
 文字のエンコードされたデータを格納するバッファーに必要な数`nSrcLen`バイトです。  
  
### <a name="remarks"></a>コメント  
 "Q"エンコーディング方式については、「RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt))。  
  
## <a name="a-nameqpdecodea-qpdecode"></a><a name="qpdecode"></a>QPDecode
前の呼び出しによってなど quoted-printable 形式にエンコードされたデータの文字列をデコード[QPEncode](#qpencode)します。  
  
```  
inline BOOL QPDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pbSrcData`  
 デコードするデータを保持するバッファー。  
  
 [入力] `nSrcLen`  
 長さのバイト数`pbSrcData`します。  
  
 [出力] `szDest`  
 デコードされたデータを受信する呼び出し元が割り当てたバッファーです。  
  
 [出力] `pnDestLen`  
 バイトの長さを格納する変数を指すポインター`szDest`します。 関数が成功した場合、変数は、バッファーに書き込まれたバイト数を受け取ります。 関数が失敗した場合、変数は、バッファーのバイト単位で、必要な長さを受信します。  
  
 [入力] `dwFlags`  
 変換を実行する方法を示すフラグ。 参照してください[ATLSMTP_QPENCODE フラグ](http://msdn.microsoft.com/library/6b15a3ab-8e57-49e4-8104-09b26ebb96c4)します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は、`TRUE` を返します。それ以外の場合は、`FALSE` を返します。  
  
### <a name="remarks"></a>コメント  
 引用符で囲まれた印刷可能なエンコード体系が RFC 2045 で説明されている ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt))。  
  
## <a name="a-nameqpdecodegetrequiredlengtha-qpdecodegetrequiredlength"></a><a name="qpdecodegetrequiredlength"></a>QPDecodeGetRequiredLength
quoted-printable にエンコードされた指定長の文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。  
  
```  
inline int QPDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードされた文字列内の文字の数。  
  
### <a name="return-value"></a>戻り値  
 デコードされた文字列を格納するバッファーの必要なバイト数`nSrcLen`文字です。  
  
### <a name="remarks"></a>コメント  
 引用符で囲まれた印刷可能なエンコード体系が RFC 2045 で説明されている ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt))。  
  
## <a name="a-nameqpencodea-qpencode"></a><a name="qpencode"></a>QPEncode
一部のデータを quoted-printable 形式にエンコードします。  
  
```  
inline BOOL QPEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   DWORD dwFlags = 0) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 `pbSrcData`  
 エンコードするデータを保持するバッファー。  
  
 `nSrcLen`  
 エンコードするデータの長さを (バイト単位)。  
  
 `szDest`  
 エンコードされたデータを受信する呼び出し元が割り当てたバッファーです。  
  
 `pnDestLen`  
 文字の長さを格納する変数へのポインター`szDest`します。 関数が成功した場合、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。  
  
 `dwFlags`  
 変換を実行する方法を示すフラグ。 参照してください[ATLSMTP_QPENCODE フラグ](http://msdn.microsoft.com/library/6b15a3ab-8e57-49e4-8104-09b26ebb96c4)します。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 引用符で囲まれた印刷可能なエンコード体系が RFC 2045 で説明されている ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt))。  
  
## <a name="a-nameqpencodegetrequiredlengtha-qpencodegetrequiredlength"></a><a name="qpencodegetrequiredlength"></a>QPEncodeGetRequiredLength
指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。  
  
```  
inline int QPEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードするデータのバイト数。  
  
### <a name="return-value"></a>戻り値  
 文字のエンコードされたデータを格納するバッファーに必要な数`nSrcLen`バイトです。  
  
### <a name="remarks"></a>コメント  
 引用符で囲まれた印刷可能なエンコード体系が RFC 2045 で説明されている ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt))。  
  
## <a name="a-nameuudecodea-uudecode"></a><a name="uudecode"></a>UUDecode
などを以前の呼び出しによって uuencode されているデータの文字列をデコード[UUEncode](#uuencode)します。  
  
```  
inline BOOL UUDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   BYTE* pbDest,  
   int* pnDestLen) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 `pbSrcData`  
 デコードするデータを含む文字列です。  
  
 `nSrcLen`  
 長さのバイト数`pbSrcData`します。  
  
 `pbDest`  
 デコードされたデータを受信する呼び出し元が割り当てたバッファーです。  
  
 `pnDestLen`  
 バイトの長さを格納する変数を指すポインター`pbDest`します。 関数が成功した場合、変数は、バッファーに書き込まれたバイト数を受け取ります。 関数が失敗した場合、変数は、バッファーのバイト単位で、必要な長さを受信します。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 この uuencoding 実装では、POSIX P1003.2b/D11 仕様に従います。  
  
## <a name="a-nameuudecodegetrequiredlengtha-uudecodegetrequiredlength"></a><a name="uudecodegetrequiredlength"></a>UUDecodeGetRequiredLength
指定した長さの uuencode された文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。  
  
```  
inline int UUDecodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードされた文字列内の文字の数。  
  
### <a name="return-value"></a>戻り値  
 デコードされた文字列を格納するバッファーの必要なバイト数`nSrcLen`文字です。  
  
### <a name="remarks"></a>コメント  
 この uuencoding 実装では、POSIX P1003.2b/D11 仕様に従います。  
  
## <a name="a-nameuuencodea-uuencode"></a><a name="uuencode"></a>UUEncode
データを uuencode します。  
  
```  
inline BOOL UUEncode(  
   const BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCTSTR lpszFile = _T("file"),  
   DWORD dwFlags = 0) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 `pbSrcData`  
 エンコードするデータを保持するバッファー。  
  
 `nSrcLen`  
 エンコードするデータの長さを (バイト単位)。  
  
 `szDest`  
 エンコードされたデータを受信する呼び出し元が割り当てたバッファーです。  
  
 `pnDestLen`  
 文字の長さを格納する変数へのポインター`szDest`します。 関数が成功した場合、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。  
  
 *プリケーション*  
 ATLSMTP_UUENCODE_HEADER がで指定した場合、ヘッダーに追加するファイル`dwFlags`します。  
  
 `dwFlags`  
 この関数の動作を制御するフラグ。 参照してください[ATLSMTP_UUENCODE フラグ](http://msdn.microsoft.com/library/ecb79b81-b764-4a48-a05c-a9dee6e7bbce)します。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 この uuencoding 実装では、POSIX P1003.2b/D11 仕様に従います。  
  
## <a name="a-nameuuencodegetrequiredlengtha-uuencodegetrequiredlength"></a><a name="uuencodegetrequiredlength"></a>UUEncodeGetRequiredLength
指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。  
  
```  
inline int UUEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードするデータのバイト数。  
  
### <a name="return-value"></a>戻り値  
 文字のエンコードされたデータを格納するバッファーに必要な数`nSrcLen`バイトです。  
  
### <a name="remarks"></a>コメント  
 この uuencoding 実装では、POSIX P1003.2b/D11 仕様に従います。  
  
### <a name="see-also"></a>関連項目  
 [概念](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)   
