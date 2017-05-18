---
title: "CA2CAEX クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CA2CAEX
- ATLCONV/ATL::CA2CAEX
- ATLCONV/ATL::CA2CAEX::CA2CAEX
- ATLCONV/ATL::CA2CAEX::m_psz
dev_langs:
- C++
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 9185bc18981898d699aa3f3eeb490c76bf5138fb
ms.contentlocale: ja-jp
ms.lasthandoff: 03/31/2017

---
# <a name="ca2caex-class"></a>CA2CAEX クラス
このクラスは、文字列変換マクロは使用`CA2CTEX`と`CT2CAEX`、および typedef **CA2CA**です。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<int t_nBufferLength = 128>  
class CA2CAEX
```  
  
#### <a name="parameters"></a>パラメーター  
 `t_nBufferLength`  
 変換プロセスで使用するバッファーのサイズ。 既定の長さは 128 バイトです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CA2CAEX::CA2CAEX](#ca2caex)|コンストラクターです。|  
|[CA2CAEX:: ~ CA2CAEX](#dtor)|デストラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CA2CAEX::operator LPCSTR](#operator_lpcstr)|変換演算子です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CA2CAEX::m_psz](#m_psz)|ソース文字列を格納するデータ メンバーです。|  
  
## <a name="remarks"></a>コメント  
 追加の機能が必要な場合を除き、使用`CA2CTEX`、 `CT2CAEX`、または**CA2CA**自分のコード。  
  
 このクラスは、安全にループで使用し、スタック オーバーフローが発生しません。 既定では、ATL 変換クラスとマクロは、現在のスレッドの ANSI コード ページを変換に使用します。  
  
 次のマクロは、このクラスに基づいています。  
  
- `CA2CTEX`  
  
- `CT2CAEX`  
  
 次の typedef は、このクラスに基づいています。  
  
- **CA2CA**  
  
 これらのテキスト変換マクロの詳細については、次を参照してください。 [ATL および MFC 文字列変換マクロ](string-conversion-macros.md)です。  
  
## <a name="example"></a>例  
 参照してください[ATL および MFC 文字列変換マクロ](string-conversion-macros.md)をこれらの文字列変換マクロを使用する例についてはします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlconv.h  
  
##  <a name="ca2caex"></a>CA2CAEX::CA2CAEX  
 コンストラクターです。  
  
```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `psz`  
 変換するテキスト文字列。  
  
 `nCodePage`  
 このクラスでは使用しません。  
  
### <a name="remarks"></a>コメント  
 変換に必要なバッファーを作成します。  
  
##  <a name="dtor"></a>CA2CAEX:: ~ CA2CAEX  
 デストラクターです。  
  
```
~CA2CAEX() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられたバッファーを解放します。  
  
##  <a name="m_psz"></a>CA2CAEX::m_psz  
 ソース文字列を格納するデータ メンバーです。  
  
```
LPCSTR m_psz;
```  
  
##  <a name="operator_lpcstr"></a>CA2CAEX::operator LPCSTR  
 変換演算子です。  
  
```  
operator LPCSTR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 種類としてテキスト文字列を返す`LPCSTR`です。  
  
## <a name="see-also"></a>関連項目  
 [CA2AEX クラス](../../atl/reference/ca2aex-class.md)   
 [CA2WEX クラス](../../atl/reference/ca2wex-class.md)   
 [CW2AEX クラス](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX クラス](../../atl/reference/cw2wex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

