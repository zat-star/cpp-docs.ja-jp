---
title: "CKeyFrame クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CKeyFrame
- CKeyFrame
dev_langs:
- C++
helpviewer_keywords:
- CKeyFrame class
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
caps.latest.revision: 18
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
ms.openlocfilehash: d8ecff2e36148fb114ee708712b6e8bd0fe558ed
ms.lasthandoff: 02/24/2017

---
# <a name="ckeyframe-class"></a>CKeyFrame クラス
アニメーションのキーフレームを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CKeyFrame : public CBaseKeyFrame;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CKeyFrame::CKeyFrame](#ckeyframe)|オーバーロードされます。 その他のキーフレームに依存するキーフレームを作成します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|ストーリー ボードにキーフレームを追加します。 (上書き[CBaseKeyFrame::AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard))。|  
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|ストーリー ボードの移行が完了後するためのキーフレームを追加します。|  
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|ストーリー ボードのオフセット位置にキーフレームを追加します。|  
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|このキーフレームによって異なりますキーフレームへのポインターを返します。|  
|[CKeyFrame::GetOffset](#getoffset)|その他のキーフレームからのオフセットを返します。|  
|[CKeyFrame::GetTransition](#gettransition)|このキーフレームが依存移行へのポインターを返します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CKeyFrame::m_offset](#m_offset)|M_pExistingKeyFrame に格納されているキーフレームから離れるときに、このキーフレームのオフセットを指定します。|  
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|既存の keframe へのポインターを格納します。 このキーフレームは、既存のキーフレームに m_offset でストーリー ボードに追加されます。|  
|[CKeyFrame::m_pTransition](#m_ptransition)|このキーフレームから開始する切り替え効果へのポインターを格納します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、アニメーションのキーフレームを実装します。 キーフレームは、ストーリー ボード内の特定の時点を表し、遷移の開始と終了時刻を指定するために使用できます。 キーフレーム他のキーフレームに基づくことが、秒単位でオフセットを持ってまたは遷移に基づいてし、この遷移の終了の時点を表します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="a-nameaddtostoryboarda--ckeyframeaddtostoryboard"></a><a name="addtostoryboard"></a>CKeyFrame::AddToStoryboard  
 ストーリー ボードにキーフレームを追加します。  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStoryboard`  
 ストーリー ボードへのポインター。  
  
 `bDeepAdd`  
 キーフレームを追加または再帰的に移行するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 キーフレームを正常に追加された場合は TRUE。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ストーリー ボードにキーフレームを追加します。 その他のキーフレームまたは遷移に依存して bDeepAdd は TRUE、このメソッドは、再帰的を追加しようとします。  
  
##  <a name="a-nameaddtostoryboardaftertransitiona--ckeyframeaddtostoryboardaftertransition"></a><a name="addtostoryboardaftertransition"></a>CKeyFrame::AddToStoryboardAfterTransition  
 ストーリー ボードの移行が完了後するためのキーフレームを追加します。  
  
```  
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStoryboard`  
 ストーリー ボードへのポインター。  
  
 `bDeepAdd`  
 遷移の再帰的に追加するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 キーフレームを正常に追加された場合は TRUE。  
  
### <a name="remarks"></a>コメント  
 この関数は、移行が完了した後ストーリー ボードにキーフレームを追加するためにフレームワークによって呼び出されます。  
  
##  <a name="a-nameaddtostoryboardatoffseta--ckeyframeaddtostoryboardatoffset"></a><a name="addtostoryboardatoffset"></a>CKeyFrame::AddToStoryboardAtOffset  
 ストーリー ボードのオフセット位置にキーフレームを追加します。  
  
```  
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStoryboard`  
 ストーリー ボードへのポインター。  
  
 `bDeepAdd`  
 キーフレームを追加するこのキーフレームが再帰的に依存するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 キーフレームを正常に追加された場合は TRUE。  
  
### <a name="remarks"></a>コメント  
 この関数は、オフセット位置にあるストーリー ボードにキーフレームを追加するためにフレームワークによって呼び出されます。  
  
##  <a name="a-nameckeyframea--ckeyframeckeyframe"></a><a name="ckeyframe"></a>CKeyFrame::CKeyFrame  
 遷移に依存するキーフレームを作成します。  
  
```  
CKeyFrame(CBaseTransition* pTransition);

 
CKeyFrame(
    CBaseKeyFrame* pKeyframe,  
    UI_ANIMATION_SECONDS offset = 0.0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTransition`  
 移行へのポインター。  
  
 `pKeyframe`  
 キーフレームへのポインター。  
  
 `offset`  
 PKeyframe で指定したキーフレームからの秒単位のオフセット。  
  
### <a name="remarks"></a>コメント  
 構築されたキーフレームは、指定した移行が終了すると、ストーリー ボード内にある時点を表します。  
  
##  <a name="a-namegetexistingkeyframea--ckeyframegetexistingkeyframe"></a><a name="getexistingkeyframe"></a>CKeyFrame::GetExistingKeyframe  
 このキーフレームによって異なりますキーフレームへのポインターを返します。  
  
```  
CBaseKeyFrame* GetExistingKeyframe();
```  
  
### <a name="return-value"></a>戻り値  
 キーフレーム、またはこのキーフレームが他のキーフレームに依存しない場合は NULL に有効なポインター。  
  
### <a name="remarks"></a>コメント  
 これは、このキーフレームによって異なりますキーフレームにアクセサーです。  
  
##  <a name="a-namegetoffseta--ckeyframegetoffset"></a><a name="getoffset"></a>CKeyFrame::GetOffset  
 その他のキーフレームからのオフセットを返します。  
  
```  
UI_ANIMATION_SECONDS GetOffset();
```  
  
### <a name="return-value"></a>戻り値  
 その他のキーフレーム間の秒単位のオフセット。  
  
### <a name="remarks"></a>コメント  
 その他のキーフレーム間の秒単位のオフセットを決定するこのメソッドを呼び出す必要があります。  
  
##  <a name="a-namegettransitiona--ckeyframegettransition"></a><a name="gettransition"></a>CKeyFrame::GetTransition  
 このキーフレームが依存移行へのポインターを返します。  
  
```  
CBaseTransition* GetTransition();
```  
  
### <a name="return-value"></a>戻り値  
 遷移、またはこのキーフレームが遷移に依存しない場合は NULL に有効なポインター。  
  
### <a name="remarks"></a>コメント  
 これは、このキーフレームによって異なります遷移にアクセサーです。  
  
##  <a name="a-namemoffseta--ckeyframemoffset"></a><a name="m_offset"></a>CKeyFrame::m_offset  
 M_pExistingKeyFrame に格納されているキーフレームから離れるときに、このキーフレームのオフセットを指定します。  
  
```  
UI_ANIMATION_SECONDS m_offset;  
```  
  
##  <a name="a-namempexistingkeyframea--ckeyframempexistingkeyframe"></a><a name="m_pexistingkeyframe"></a>CKeyFrame::m_pExistingKeyFrame  
 既存の keframe へのポインターを格納します。 このキーフレームは、既存のキーフレームに m_offset でストーリー ボードに追加されます。  
  
```  
CBaseKeyFrame* m_pExistingKeyFrame;  
```  
  
##  <a name="a-namemptransitiona--ckeyframemptransition"></a><a name="m_ptransition"></a>CKeyFrame::m_pTransition  
 このキーフレームから開始する切り替え効果へのポインターを格納します。  
  
```  
CBaseTransition* m_pTransition;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

