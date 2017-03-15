---
title: "CW2WEX クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CW2WEX
- ATL.CW2WEX<t_nBufferLength>
- ATL::CW2WEX
- ATL.CW2WEX
- ATL::CW2WEX<t_nBufferLength>
dev_langs:
- C++
helpviewer_keywords:
- CW2WEX class
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 9382f8404c1469b3f847500f35ab26499b6579bc
ms.lasthandoff: 02/24/2017

---
# <a name="cw2wex-class"></a>CW2WEX クラス
このクラスは、文字列変換マクロによって使用`CW2TEX`と`CT2WEX`、および typedef`CW2W`します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <int t_nBufferLength = 128>  
class CW2WEX
```  
  
#### <a name="parameters"></a>パラメーター  
 `t_nBufferLength`  
 変換プロセスで使用されるバッファーのサイズ。 既定の長さは、128 バイトです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CW2WEX::CW2WEX](#cw2wex)|コンストラクターです。|  
|[CW2WEX:: ~ CW2WEX](#dtor)|デストラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CW2WEX::operator LPWSTR](#operator_lpwstr)|変換演算子。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CW2WEX::m_psz](#m_psz)|ソース文字列を格納するデータ メンバー。|  
|[CW2WEX::m_szBuffer](#m_szbuffer)|静的バッファー、変換後の文字列を格納するために使用します。|  
  
## <a name="remarks"></a>コメント  
 追加の機能が必要な場合を除き、使用`CW2TEX`、 `CT2WEX`、または`CW2W`コードにします。  
  
 このクラスには、変換の結果を格納するために使用される固定サイズの静的バッファーが含まれています。 結果が大きすぎて静的バッファーに収まらない場合、クラスは `malloc` を使用してメモリを割り当て、オブジェクトがスコープから外れときにそのメモリを解放します。 これにより、テキストとは異なり、ATL のこのクラスは、安全にループ内で使用して、スタックがオーバーフローすることはありませんの以前のバージョンで使用できる変換マクロ。  
  
 クラスは、失敗、ヒープにメモリを割り当てるしようとすると、それが呼び出す`AtlThrow`の引数を持つ**E_OUTOFMEMORY**します。  
  
 既定では、ATL 変換クラスとマクロは、変換のため現在のスレッドの ANSI コード ページを使用します。  
  
 次のマクロは、このクラスに基づいています。  
  
- `CW2TEX`  
  
- `CT2WEX`  
  
 次の typedef は、このクラスに基づいています。  
  
- `CW2W`  
  
 これらのテキスト変換マクロの詳細については、次を参照してください。 [ATL と MFC 文字列変換マクロ](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863)します。  
  
## <a name="example"></a>例  
 参照してください[ATL と MFC 文字列変換マクロ](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863)のこれらの文字列変換マクロを使用する例です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlconv.h  
  
##  <a name="a-namecw2wexa--cw2wexcw2wex"></a><a name="cw2wex"></a>CW2WEX::CW2WEX  
 コンストラクターです。  
  
```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `psz`  
 変換するテキスト文字列。  
  
 `nCodePage`  
 コード ページです。 このクラスでは使用されません。  
  
### <a name="remarks"></a>コメント  
 変換に必要なバッファーを作成します。  
  
##  <a name="a-namedtora--cw2wexcw2wex"></a><a name="dtor"></a>CW2WEX:: ~ CW2WEX  
 デストラクターは、.  
  
```
~CW2WEX() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられたバッファーを解放します。  
  
##  <a name="a-namempsza--cw2wexmpsz"></a><a name="m_psz"></a>CW2WEX::m_psz  
 ソース文字列を格納するデータ メンバー。  
  
```
LPWSTR m_psz;
```  
  
##  <a name="a-namemszbuffera--cw2wexmszbuffer"></a><a name="m_szbuffer"></a>CW2WEX::m_szBuffer  
 静的バッファー、変換後の文字列を格納するために使用します。  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="a-nameoperatorlpwstra--cw2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a>CW2WEX::operator LPWSTR  
 キャスト演算子です。  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 文字列を型として返します`LPWSTR`します。  
  
## <a name="see-also"></a>関連項目  
 [CA2AEX クラス](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX クラス](../../atl/reference/ca2caex-class.md)   
 [CA2WEX クラス](../../atl/reference/ca2wex-class.md)   
 [CW2AEX クラス](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

