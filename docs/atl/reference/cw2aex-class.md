---
title: "CW2AEX クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CW2AEX<t_nBufferLength>
- CW2AEX
- ATL.CW2AEX<t_nBufferLength>
- ATL::CW2AEX
- ATL.CW2AEX
dev_langs:
- C++
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8bf433224396f54b81fb5310ec29dfed213c6855
ms.lasthandoff: 02/24/2017

---
# <a name="cw2aex-class"></a>CW2AEX クラス
このクラスは、文字列変換マクロによって使用`CT2AEX`、 `CW2TEX`、 `CW2CTEX`、および`CT2CAEX`、および typedef **CW2A**します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<int t_nBufferLength = 128>  
class CW2AEX
```  
  
#### <a name="parameters"></a>パラメーター  
 `t_nBufferLength`  
 変換プロセスで使用されるバッファーのサイズ。 既定の長さは、128 バイトです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CW2AEX::CW2AEX](#cw2aex)|コンストラクターです。|  
|[CW2AEX:: ~ CW2AEX](#dtor)|デストラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CW2AEX::operator LPSTR](#operator_lpstr)|変換演算子。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CW2AEX::m_psz](#m_psz)|ソース文字列を格納するデータ メンバー。|  
|[CW2AEX::m_szBuffer](#m_szbuffer)|静的バッファー、変換後の文字列を格納するために使用します。|  
  
## <a name="remarks"></a>コメント  
 追加の機能が必要な場合を除き、使用`CT2AEX`、 `CW2TEX`、 `CW2CTEX`、 `CT2CAEX`、または**CW2A**コードにします。  
  
 このクラスには、変換の結果を格納するために使用される固定サイズの静的バッファーが含まれています。 結果が大きすぎて静的バッファーに収まらない場合、クラスは `malloc` を使用してメモリを割り当て、オブジェクトがスコープから外れときにそのメモリを解放します。 これにより、テキストとは異なり、ATL のこのクラスは、安全にループ内で使用して、スタックがオーバーフローすることはありませんの以前のバージョンで使用できる変換マクロ。  
  
 クラスは、失敗、ヒープにメモリを割り当てるしようとすると、それが呼び出す`AtlThrow`の引数を持つ**E_OUTOFMEMORY**します。  
  
 既定では、ATL 変換クラスとマクロは、変換のため現在のスレッドの ANSI コード ページを使用します。 特定の変換の動作をオーバーライドする場合は、クラスのコンス トラクターの&2; 番目のパラメーターとしてコード ページを指定します。  
  
 次のマクロは、このクラスに基づいています。  
  
- `CT2AEX`  
  
- `CW2TEX`  
  
- `CW2CTEX`  
  
- `CT2CAEX`  
  
 次の typedef は、このクラスに基づいています。  
  
- **CW2A**  
  
 これらのテキスト変換マクロの詳細については、次を参照してください。 [ATL と MFC 文字列変換マクロ](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863)します。  
  
## <a name="example"></a>例  
 参照してください[ATL と MFC 文字列変換マクロ](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863)のこれらの文字列変換マクロを使用する例です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlconv.h  
  
##  <a name="a-namecw2aexa--cw2aexcw2aex"></a><a name="cw2aex"></a>CW2AEX::CW2AEX  
 コンストラクターです。  
  
```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2AEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `psz`  
 変換するテキスト文字列。  
  
 `nCodePage`  
 コード ページ変換を実行するために使用します。 コード ページ パラメーターの説明を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]関数[MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)詳細です。  
  
### <a name="remarks"></a>コメント  
 変換処理で使用するバッファーを割り当てます。  
  
##  <a name="a-namedtora--cw2aexcw2aex"></a><a name="dtor"></a>CW2AEX:: ~ CW2AEX  
 デストラクターです。  
  
```
~CW2AEX() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられたバッファーを解放します。  
  
##  <a name="a-namempsza--cw2aexmpsz"></a><a name="m_psz"></a>CW2AEX::m_psz  
 ソース文字列を格納するデータ メンバー。  
  
```
LPSTR m_psz;
```  
  
##  <a name="a-namemszbuffera--cw2aexmszbuffer"></a><a name="m_szbuffer"></a>CW2AEX::m_szBuffer  
 静的バッファー、変換後の文字列を格納するために使用します。  
  
```
char m_szBuffer[t_nBufferLength];
```  
  
##  <a name="a-nameoperatorlpstra--cw2aexoperator-lpstr"></a><a name="operator_lpstr"></a>CW2AEX::operator LPSTR  
 変換演算子。  
  
```  
operator LPSTR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 文字列を型として返します**LPSTR です。**  
  
## <a name="see-also"></a>関連項目  
 [CA2AEX クラス](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX クラス](../../atl/reference/ca2caex-class.md)   
 [CA2WEX クラス](../../atl/reference/ca2wex-class.md)   
 [CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX クラス](../../atl/reference/cw2wex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

