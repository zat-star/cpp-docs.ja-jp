---
title: "CA2WEX クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATLCONV/CA2WEX
- ATL.CA2WEX
- ATL.CA2WEX<t_nBufferLength>
- ATL::CA2WEX
- ATL::CA2WEX<t_nBufferLength>
- CA2WEX
dev_langs:
- C++
helpviewer_keywords:
- CA2WEX class
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 7c1029d0d9cb1abb1980f97c9541e2c1ce40b539
ms.lasthandoff: 02/24/2017

---
# <a name="ca2wex-class"></a>CA2WEX クラス
このクラスは、文字列変換マクロによって使用`CA2TEX`、 `CA2CTEX`、 `CT2WEX`、および`CT2CWEX`、および typedef **CA2W**します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <int t_nBufferLength = 128>
class CA2WEX
```  
  
#### <a name="parameters"></a>パラメーター  
 `t_nBufferLength`  
 変換プロセスで使用されるバッファーのサイズ。 既定の長さは、128 バイトです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CA2WEX::CA2WEX](#ca2wex)|コンストラクターです。|  
|[CA2WEX:: ~ CA2WEX](#dtor)|デストラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CA2WEX::operator LPWSTR](#operator_lpwstr)|変換演算子。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CA2WEX::m_psz](#m_psz)|ソース文字列を格納するデータ メンバー。|  
|[CA2WEX::m_szBuffer](#m_szbuffer)|静的バッファー、変換後の文字列を格納するために使用します。|  
  
## <a name="remarks"></a>コメント  
 追加の機能が必要な場合を除き、使用`CA2TEX`、 `CA2CTEX`、 `CT2WEX`、 `CT2CWEX`、または**CA2W**コードにします。  
  
 このクラスには、変換の結果を格納するために使用される固定サイズの静的バッファーが含まれています。 結果が大きすぎて静的バッファーに収まらない場合、クラスは `malloc` を使用してメモリを割り当て、オブジェクトがスコープから外れときにそのメモリを解放します。 これにより、テキストとは異なり、ATL のこのクラスは、安全にループ内で使用して、スタックがオーバーフローすることはありませんの以前のバージョンで使用できる変換マクロ。  
  
 クラスは、失敗、ヒープにメモリを割り当てるしようとすると、それが呼び出す`AtlThrow`の引数を持つ**E_OUTOFMEMORY**します。  
  
 既定では、ATL 変換クラスとマクロは、変換のため現在のスレッドの ANSI コード ページを使用します。 特定の変換の動作をオーバーライドする場合は、クラスのコンス トラクターの&2; 番目のパラメーターとしてコード ページを指定します。  
  
 次のマクロは、このクラスに基づいています。  
  
- `CA2TEX`  
  
- `CA2CTEX`  
  
- `CT2WEX`  
  
- `CT2CWEX`  
  
 次の typedef は、このクラスに基づいています。  
  
- **CA2W**  
  
 これらのテキスト変換マクロの詳細については、次を参照してください。 [ATL と MFC 文字列変換マクロ](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863)します。  
  
## <a name="example"></a>例  
 参照してください[ATL と MFC 文字列変換マクロ](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863)のこれらの文字列変換マクロを使用する例です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlconv.h  
  
##  <a name="a-nameca2wexa--ca2wexca2wex"></a><a name="ca2wex"></a>CA2WEX::CA2WEX  
 コンストラクターです。  
  
```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `psz`  
 変換するテキスト文字列。  
  
 `nCodePage`  
 コード ページ変換を実行するために使用します。 コード ページ パラメーターの説明を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]関数[MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)詳細です。  
  
### <a name="remarks"></a>コメント  
 変換処理で使用するバッファーを割り当てます。  
  
##  <a name="a-namedtora--ca2wexca2wex"></a><a name="dtor"></a>CA2WEX:: ~ CA2WEX  
 デストラクターです。  
  
```
~CA2WEX() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられたバッファーを解放します。  
  
##  <a name="a-namempsza--ca2wexmpsz"></a><a name="m_psz"></a>CA2WEX::m_psz  
 ソース文字列を格納するデータ メンバー。  
  
```
LPWSTR m_psz;
```  
  
##  <a name="a-namemszbuffera--ca2wexmszbuffer"></a><a name="m_szbuffer"></a>CA2WEX::m_szBuffer  
 静的バッファー、変換後の文字列を格納するために使用します。  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="a-nameoperatorlpwstra--ca2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a>CA2WEX::operator LPWSTR  
 変換演算子。  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 文字列を型として返します**LPWSTR します。**  
  
## <a name="see-also"></a>関連項目  
 [CA2AEX クラス](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX クラス](../../atl/reference/ca2caex-class.md)   
 [CW2AEX クラス](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX クラス](../../atl/reference/cw2wex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

