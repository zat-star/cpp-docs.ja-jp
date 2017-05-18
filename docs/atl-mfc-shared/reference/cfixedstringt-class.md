---
title: "CFixedStringT クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
dev_langs:
- C++
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
caps.latest.revision: 17
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f357a70a728b388c3b5d3d26ac4efd0d4c84434a
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cfixedstringt-class"></a>CFixedStringT クラス
このクラスは、固定された文字バッファーを持つ文字列オブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```  
  
#### <a name="parameters"></a>パラメーター  
 `StringType`  
 固定文字列オブジェクトの基本クラスとして使用し、いずれかになります`CStringT`-ベースの型。 例として、 `CString`、 `CStringA`、および`CStringW`です。  
  
 *t_nChars*  
 バッファーに格納されている文字数。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFixedStringT::CFixedStringT](#cfixedstringt)|文字列オブジェクトのコンス トラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CFixedStringT::operator =](#eq)|新しい値を代入する`CFixedStringT`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 このクラスに基づくカスタム文字列クラスの例は、`CStringT`です。 きわめて似ていますが、2 つのクラスは実装こそ異なります。 主な相違`CFixedStringT`と`CStringT`は。  
  
-   最初の文字バッファーは、オブジェクトの一部として割り当てられているし、サイズが*t_nChars*します。 これにより、 **CFixedString**パフォーマンス向上のための連続したメモリのチャンクを占有するオブジェクト。 ただし場合の内容、`CFixedStringT`オブジェクトを超えた*t_nChars*バッファーが動的に割り当てられます。  
  
-   文字バッファーを`CFixedStringT`オブジェクトが同じ長さでは常に ( *t_nChars*)。 バッファー サイズに制限はありません`CStringT`オブジェクトです。  
  
-   メモリ マネージャー`CFixedStringT`を共有するようにカスタマイズされた、 [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)の&2; つ以上のオブジェクト`CFixedStringT`objectsis が許可されていません。 `CStringT`オブジェクトには、この制限はありません。  
  
 詳細のカスタマイズについて`CFixedStringT`文字列オブジェクトのメモリ管理は一般を参照してくださいと[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IAtlStringMgr`  
  
 `StringType`  
  
 `CFixedStringMgr`  
  
 `CFixedStringT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** cstringt.h  
  
##  <a name="cfixedstringt"></a>CFixedStringT::CFixedStringT  
 `CFixedStringT` オブジェクトを構築します。  
  
```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT(const StringType& str);
CFixedStringT(const StringType::XCHAR* psz);
explicit CFixedStringT(const StringType::YCHAR* psz);
explicit CFixedStringT(const unsigned char* psz);
```  
  
### <a name="parameters"></a>パラメーター  
 `psz`  
 これにコピーされる null で終わる文字列`CFixedStringT`オブジェクトです。  
  
 `str`  
 既存の`CFixedStringT`オブジェクトにコピーされる`CFixedStringT`オブジェクトです。  
  
 `pStringMgr`  
 メモリ マネージャーへのポインター、`CFixedStringT`オブジェクトです。 詳細については`IAtlStringMgr`とメモリ管理を`CFixedStringT`を参照してください[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターは、入力データを新しい割り当て済み記憶域にコピー、するために注意してくださいメモリ不足の例外が発生する可能性があります。 変換関数として機能するこれらのコンス トラクターのいくつか注意してください。  
  
##  <a name="operator__eq"></a>CFixedStringT::operator =  
 既存の再初期化`CFixedStringT`オブジェクトに新しいデータ。  
  
```
CFixedStringT<StringType, t_nChars>& operator=(
  const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT<StringType, t_nChars>& operator=(const char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* psz);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& str);
```  
  
### <a name="parameters"></a>パラメーター  
 `str`  
 これにコピーされる null で終わる文字列`CFixedStringT`オブジェクトです。  
  
 `psz`  
 既存の`CFixedStringT`これにコピーされる`CFixedStringT`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 注意すべき、代入演算子を使用すると、新しいストレージが多くの場合、その結果を保持するために割り当てられているために、例外が発生するメモリ`CFixedStringT`オブジェクトです。  
  
## <a name="see-also"></a>関連項目  
 [CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL と MFC クラスの共有](../../atl-mfc-shared/atl-mfc-shared-classes.md)





