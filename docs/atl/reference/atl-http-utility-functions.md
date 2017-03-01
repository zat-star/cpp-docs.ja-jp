---
title: "ATL HTTP ユーティリティ関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
caps.latest.revision: 4
author: mikeblome
ms.author: mblome
translationtype: Machine Translation
ms.sourcegitcommit: 9ab4b38b2ba14aca2240d12fff966d36750a3229
ms.openlocfilehash: dd8b3a279148e2a5b72d96724c329e49cd5d3e5f
ms.lasthandoff: 02/24/2017

---
# <a name="atl-http-utility-functions"></a>ATL HTTP ユーティリティ関数

これらの関数は、Url の操作をサポートします。

|||  
|-|-|  
|[どうか](#atlcanonicalizeurl)|安全でない文字や空白をエスケープ シーケンスに変換を含む URL を正規化します。|  
|[AtlCombineUrl](#atlcombineurl)|1 つの標準形式の URL には、ベース URL と相対 URL を結合します。|  
|[AtlEscapeUrl](#atlescapeurl)|すべての安全でない文字をエスケープ シーケンスに変換します。|  
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|特定のインターネット プロトコルまたはスキームに関連付けられている既定のポート番号を取得します。|  
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|文字を URL で使用しても安全かどうかを判断します。|  
|[AtlUnescapeUrl](#atlunescapeurl)|エスケープ文字を元の値に変換します。|  
|[RGBToHtml](#rgbtohtml)|変換、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値をそのカラー値に対応する HTML テキスト。|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|システム時刻を HTTP ヘッダーで使用できる形式の文字列に変換します。|

## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  

## <a name="a-nameatlcanonicalizeurla-atlcanonicalizeurl"></a><a name="atlcanonicalizeurl"></a>どうか
URL を標準形式に変換します。安全でない文字や空白をエスケープ シーケンスに変換する処理などが含まれます。  
  
```    
inline BOOL AtlCanonicalizeUrl(  
   LPCTSTR szUrl,  
   LPTSTR szCanonicalized,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `szUrl`  
 正規化される URL です。  
  
 `szCanonicalized`  
 正規化された URL を受信する呼び出し元が割り当てたバッファーです。  
  
 `pdwMaxLength`  
 文字の長さを格納する変数へのポインター`szCanonicalized`します。 関数が成功した場合、変数は、終端の null 文字を含まないバッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、終端の null 文字の空白を含むバッファーのバイト単位で、必要な長さを受信します。  
  
 `dwFlags`  
 この関数の動作を制御するフラグ。 参照してください[ATL_URL フラグ](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7)します。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 現在のバージョンのように動作[InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342) WinInet または Internet Explorer をインストールするのには必要ありません。  
  
### <a name="see-also"></a>関連項目  
 [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342)

 ## <a name="a-nameatlcombineurla-atlcombineurl"></a><a name="atlcombineurl"></a>AtlCombineUrl
 ベース URL と相対 URL を結合して、1 つの標準形式の URL にします。  
  
```    
inline BOOL AtlCombineUrl(  
   LPCTSTR szBaseUrl,  
   LPCTSTR szRelativeUrl,  
   LPTSTR szBuffer,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *szBaseUrl*  
 ベース URL。  
  
 *szRelativeUrl*  
 ベース URL に相対 URL です。  
  
 `szBuffer`  
 正規化された URL を受信する呼び出し元が割り当てたバッファーです。  
  
 `pdwMaxLength`  
 文字の長さを格納する変数へのポインター`szBuffer`します。 関数が成功した場合、変数は、終端の null 文字を含まないバッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、終端の null 文字の空白を含むバッファーのバイト単位で、必要な長さを受信します。  
  
 `dwFlags`  
 この関数の動作を制御するフラグ。 参照してください[ATL_URL フラグ](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7)します。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 現在のバージョンのように動作[InternetCombineUrl](http://msdn.microsoft.com/library/windows/desktop/aa384355) WinInet または Internet Explorer をインストールするのには必要ありません。  
  
## <a name="a-nameatlescapeurla-atlescapeurl"></a><a name="atlescapeurl"></a>AtlEscapeUrl
 すべての安全でない文字をエスケープ シーケンスに変換します。  
  
```    
inline BOOL AtlEscapeUrl(  
   LPCSTR szStringIn,  
   LPSTR szStringOut,  
   DWORD* pdwStrLen,  
   DWORD dwMaxLength,  
   DWORD dwFlags = 0) throw();  
   
inline BOOL AtlEscapeUrl(  
   LPCWSTR szStringIn,  
   LPWSTR szStringOut,  
   DWORD* pdwStrLen,  
   DWORD dwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszStringIn`  
 変換する URL です。  
  
 `lpszStringOut`  
 変換された URL の書き込み先となる、呼び出し元が割り当てたバッファーです。  
  
 `pdwStrLen`  
 DWORD 変数へのポインター。 関数が成功すると、`pdwStrLen`は終端の null 文字を含まない、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、終端の null 文字の空白を含むバッファーのバイト単位で、必要な長さを受信します。 このメソッドのワイド文字バージョンを使用して`pdwStrLen`番号は、文字が、必要なバイト数ではありません。  
  
 `dwMaxLength`  
 バッファーのサイズ`lpszStringOut`します。  
  
 `dwFlags`  
 この関数の動作を制御するフラグ。 参照してください[ATL_URL フラグ](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7)します。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
## <a name="atlgetdefaulturlport"></a> 
 特定のインターネット プロトコルまたはスキームに関連付けられた、既定のポート番号を取得します。  
  
```  
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *m_nScheme*  
 [ATL_URL_SCHEME](atl-url-scheme-enum.md)ポート番号を取得するパターンを識別する値。  
  
### <a name="return-value"></a>戻り値  
 [ATL_URL_PORT](atl-typedefs.md#atl_url_port)スキームが認識されない場合は、指定されたスキームまたは ATL_URL_INVALID_PORT_NUMBER に関連付けられています。  

## <a name="a-nameatlisunsafeurlchara-atlisunsafeurlchar"></a><a name="atlisunsafeurlchar"></a>AtlIsUnsafeUrlChar
 URL で使用しても安全な文字かどうかを判断します。  
  
```  
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `chIn`  
 安全性をテストする文字。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**入力文字が安全でない場合**FALSE**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 文字を Url で使用する必要がありますがこの関数を使用してテストすることができを使用して変換[どうか](#atlcanonicalizeurl)します。  
  
## <a name="a-nameatlunescapeurla-atlunescapeurl"></a><a name="atlunescapeurl"></a>AtlUnescapeUrl
 エスケープされた文字を元の値に変換します。  
  
```    
inline BOOL AtlUnescapeUrl(  
   LPCSTR szStringIn,  
   LPSTR szStringOut,  
   LPDWORD pdwStrLen,  
   DWORD dwMaxLength) throw();  

inline BOOL AtlUnescapeUrl(  
   LPCWSTR szStringIn,  
   LPWSTR szStringOut,  
   LPDWORD pdwStrLen,  
   DWORD dwMaxLength) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszStringIn`  
 変換する URL です。  
  
 `lpszStringOut`  
 変換された URL の書き込み先となる、呼び出し元が割り当てたバッファーです。  
  
 `pdwStrLen`  
 DWORD 変数へのポインター。 関数が成功した場合、変数は、終端の null 文字を含まないバッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、終端の null 文字の空白を含むバッファーのバイト単位で、必要な長さを受信します。  
  
 `dwMaxLength`  
 バッファーのサイズ`lpszStringOut`します。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 によって適用される変換プロセスを反転[AtlEscapeUrl](#atlescapeurl)します。  
  
## <a name="a-namergbtohtmla-rgbtohtml"></a><a name="rgbtohtml"></a>RGBToHtml
変換、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値をそのカラー値に対応する HTML テキスト。  
  
```  
bool inline RGBToHtml(  
   COLORREF color,  
   LPTSTR pbOut,  
   long nBuffer);  
```  
  
### <a name="parameters"></a>パラメーター  
 `color`  
 RGB 色の値。  
  
 `pbOut`  
 HTML のカラー値のテキストを受け取る呼び出し元が割り当てたバッファーです。 バッファーの領域が必要には、少なくとも 8 文字の null ターミネータの空白を含む)。  
  
 *nBuffer*  
 (Null 終端文字の空白を含む) バッファーのバイト単位のサイズ。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 HTML のカラー値は、各色の赤、緑、および青のコンポーネントの 2 桁の数字を使用して、6 桁の 16 進数値の前にシャープ記号 (たとえば、#FFFFFF は白)。  
  
## <a name="a-namesystemtimetohttpdatea-systemtimetohttpdate"></a><a name="systemtimetohttpdate"></a>SystemTimeToHttpDate
システム時刻を HTTP ヘッダーで使用できる形式の文字列に変換します。  
  
```  
inline void SystemTimeToHttpDate( 
   const SYSTEMTIME& st,  
   CStringA& strTime);  
```  
  
### <a name="parameters"></a>パラメーター  
 `st`  
 HTTP の書式指定文字列として取得するためのシステム時刻。  
  
 *strTime*  
 RFC 2616 で定義されているように、日付時刻を HTTP に受け取るように文字列変数への参照 ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) および RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt))。  
  
## <a name="see-also"></a>関連項目  
 [概念](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)   


