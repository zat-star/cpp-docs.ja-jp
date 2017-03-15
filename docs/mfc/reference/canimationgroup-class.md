---
title: "CAnimationGroup クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CAnimationGroup
- CAnimationGroup
dev_langs:
- C++
helpviewer_keywords:
- CAnimationGroup class
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a59d8a86fde68510d48e4a3398b6590b2215cbea
ms.lasthandoff: 02/24/2017

---
# <a name="canimationgroup-class"></a>CAnimationGroup クラス
アニメーション ストーリー ボード、アニメーション オブジェクト、およびアニメーションを定義する切り替え効果を組み合わせたアニメーション グループを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationGroup;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationGroup::CAnimationGroup](#canimationgroup)|アニメーション グループを作成します。|  
|[CAnimationGroup:: ~ CAnimationGroup](#canimationgroup__~canimationgroup)|デストラクターです。 アニメーション グループが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationGroup::Animate](#animate)|グループをアニメーション化します。|  
|[CAnimationGroup::ApplyTransitions](#applytransitions)|アニメーション オブジェクトへの遷移を適用します。|  
|[CAnimationGroup::FindAnimationObject](#findanimationobject)|指定したアニメーション変数を含むアニメーション オブジェクトを検索します。|  
|[CAnimationGroup::GetGroupID](#getgroupid)|グループ Id を返します。|  
|[CAnimationGroup::RemoveKeyframes](#removekeyframes)|削除し、必要に応じてアニメーション グループに属しているすべてのキーフレームを破棄します。|  
|[CAnimationGroup::RemoveTransitions](#removetransitions)|アニメーション グループに属しているアニメーション オブジェクトからの遷移を削除します。|  
|[CAnimationGroup::Schedule](#schedule)|指定された時間にアニメーションをスケジュールします。|  
|[CAnimationGroup::SetAutodestroyTransitions](#setautodestroytransitions)|自動的にグループに属するすべてのアニメーション オブジェクトの遷移を破棄するように指示します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationGroup::AddKeyframes](#addkeyframes)|ストーリー ボードにキーフレームを追加するためのヘルパーです。|  
|[CAnimationGroup::AddTransitions](#addtransitions)|ストーリー ボードに遷移を追加するためのヘルパーです。|  
|[CAnimationGroup::CreateTransitions](#createtransitions)|遷移の COM オブジェクトを作成するためのヘルパーです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationGroup::m_bAutoclearTransitions](#m_bautocleartransitions)|グループに属しているアニメーション オブジェクトからの移行をオフにする方法を指定します。 このメンバーが TRUE の場合、アニメーションがスケジュールされているときに、遷移自動的に削除されます。 それ以外の場合は、遷移を手動で削除する必要があります。|  
|[CAnimationGroup::m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|アニメーション オブジェクトを破棄する方法を指定します。 このパラメーターが TRUE の場合、グループが破棄されるときに、アニメーション オブジェクトが自動的に破棄されます。 それ以外の場合のアニメーション オブジェクトを手動で破壊する必要があります。 既定値は FALSE です。 New 演算子をグループに属しているすべてのアニメーション オブジェクトが動的に割り当てられる場合にのみ、この値を TRUE に設定します。|  
|[CAnimationGroup::m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|キーフレームを破棄する方法を指定します。 すべてのキーフレームが削除され、破棄されます。 この値が TRUE の場合は、それ以外の場合のみが一覧から削除されます。 既定値は TRUE です。|  
|[CAnimationGroup::m_lstAnimationObjects](#m_lstanimationobjects)|アニメーション オブジェクトの一覧が含まれています。|  
|[CAnimationGroup::m_lstKeyFrames](#m_lstkeyframes)|キーフレームの一覧が含まれています。|  
|[CAnimationGroup::m_pStoryboard](#m_pstoryboard)|アニメーション ストーリー ボードへのポインター。 このポインターは、アニメーションの呼び出し後にのみ有効です。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationGroup::m_nGroupID](#m_ngroupid)|アニメーションのグループの一意の識別子。|  
|[CAnimationGroup::m_pParentController](#m_pparentcontroller)|このグループに属しているアニメーション コント ローラーへのポインター。|  
  
## <a name="remarks"></a>コメント  
 アニメーション グループは、CAnimationController::AddAnimationObject を使用して、アニメーション オブジェクトを追加する場合も、アニメーション コント ローラー (CAnimationController) によって自動的に作成されます。 アニメーション グループは、通常、アニメーションのグループを操作パラメーターとして取得された GroupID で識別されます。 GroupID は、新しいアニメーション グループに追加される最初のアニメーション オブジェクトから取得されます。 CAnimationController::AnimateGroup を呼び出すし、パブリック メンバー m_pStoryboard 経由でアクセスできる、カプセル化されたアニメーション ストーリー ボードが作成されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CAnimationGroup`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="a-namedtorcanimationgroupa--canimationgroupcanimationgroup"></a><a name="_dtorcanimationgroup"></a>CAnimationGroup:: ~ CAnimationGroup  
 デストラクターです。 アニメーション グループが破棄されるときに呼び出されます。  
  
```  
~CAnimationGroup();
```  
  
##  <a name="a-nameaddkeyframesa--canimationgroupaddkeyframes"></a><a name="addkeyframes"></a>CAnimationGroup::AddKeyframes  
 ストーリー ボードにキーフレームを追加するためのヘルパーです。  
  
```  
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStoryboard`  
 ストーリー ボード COM オブジェクトへのポインター。  
  
 `bAddDeep`  
 このメソッドは、他のキーフレームに依存しているストーリー ボードのキーフレームに追加する必要があるかどうかを指定します。  
  
##  <a name="a-nameaddtransitionsa--canimationgroupaddtransitions"></a><a name="addtransitions"></a>CAnimationGroup::AddTransitions  
 ストーリー ボードに遷移を追加するためのヘルパーです。  
  
```  
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStoryboard`  
 ストーリー ボード COM オブジェクトへのポインター。  
  
 `bDependOnKeyframes`  
  
##  <a name="a-nameanimatea--canimationgroupanimate"></a><a name="animate"></a>CAnimationGroup::Animate  
 グループをアニメーション化します。  
  
```  
BOOL Animate(
    IUIAnimationManager* pManager,  
    IUIAnimationTimer* pTimer,  
    BOOL bScheduleNow);
```  
  
### <a name="parameters"></a>パラメーター  
 `pManager`  
 `pTimer`  
 `bScheduleNow`  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、内部のストーリー ボードを作成、作成し、遷移を適用したうえで、bScheduleNow が TRUE の場合、アニメーションのスケジュールを設定します。 BScheduleNow が FALSE の場合は、指定された時間にアニメーションを開始するようにスケジュールを呼び出す必要があります。  
  
##  <a name="a-nameapplytransitionsa--canimationgroupapplytransitions"></a><a name="applytransitions"></a>CAnimationGroup::ApplyTransitions  
 アニメーション オブジェクトへの遷移を適用します。  
  
```  
void ApplyTransitions();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ストーリー ボードが作成されていないかどうかはデバッグ モードでアサートします。 最初に、すべての遷移を作成し、「静的」キーフレーム (オフセットに依存するキーフレーム) が追加、キーフレームに依存しない遷移を追加、遷移によってキーフレームとその他のキーフレームを追加およびキーフレームに依存する遷移が最後に追加します。  
  
##  <a name="a-namecanimationgroupa--canimationgroupcanimationgroup"></a><a name="canimationgroup"></a>CAnimationGroup::CAnimationGroup  
 アニメーション グループを作成します。  
  
```  
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentController`  
 グループを作成するアニメーション コント ローラーへのポインター。  
  
 `nGroupID`  
 グループ Id を指定します。  
  
##  <a name="a-namecreatetransitionsa--canimationgroupcreatetransitions"></a><a name="createtransitions"></a>CAnimationGroup::CreateTransitions  
 遷移の COM オブジェクトを作成するためのヘルパーです。  
  
```  
BOOL CreateTransitions();
```  
  
### <a name="return-value"></a>戻り値  
 TRUE では、メソッドが成功した場合は FALSE です。  
  
##  <a name="a-namefindanimationobjecta--canimationgroupfindanimationobject"></a><a name="findanimationobject"></a>CAnimationGroup::FindAnimationObject  
 指定したアニメーション変数を含むアニメーション オブジェクトを検索します。  
  
```  
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>パラメーター  
 `pVariable`  
 アニメーション変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 アニメーション オブジェクト、またはアニメーション オブジェクトが見つからない場合は NULL へのポインター。  
  
##  <a name="a-namegetgroupida--canimationgroupgetgroupid"></a><a name="getgroupid"></a>CAnimationGroup::GetGroupID  
 グループ Id を返します。  
  
```  
UINT32 GetGroupID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 グループの識別子です。  
  
##  <a name="a-namembautocleartransitionsa--canimationgroupmbautocleartransitions"></a><a name="m_bautocleartransitions"></a>CAnimationGroup::m_bAutoclearTransitions  
 グループに属しているアニメーション オブジェクトからの移行をオフにする方法を指定します。 このメンバーが TRUE の場合、アニメーションがスケジュールされているときに、遷移自動的に削除されます。 それ以外の場合は、遷移を手動で削除する必要があります。  
  
```  
BOOL m_bAutoclearTransitions;  
```  
  
##  <a name="a-namembautodestroyanimationobjectsa--canimationgroupmbautodestroyanimationobjects"></a><a name="m_bautodestroyanimationobjects"></a>CAnimationGroup::m_bAutodestroyAnimationObjects  
 アニメーション オブジェクトを破棄する方法を指定します。 このパラメーターが TRUE の場合、グループが破棄されるときに、アニメーション オブジェクトが自動的に破棄されます。 それ以外の場合のアニメーション オブジェクトを手動で破壊する必要があります。 既定値は FALSE です。 New 演算子をグループに属しているすべてのアニメーション オブジェクトが動的に割り当てられる場合にのみ、この値を TRUE に設定します。  
  
```  
BOOL m_bAutodestroyAnimationObjects;  
```  
  
##  <a name="a-namembautodestroykeyframesa--canimationgroupmbautodestroykeyframes"></a><a name="m_bautodestroykeyframes"></a>CAnimationGroup::m_bAutodestroyKeyframes  
 キーフレームを破棄する方法を指定します。 すべてのキーフレームが削除され、破棄されます。 この値が TRUE の場合は、それ以外の場合のみが一覧から削除されます。 既定値は TRUE です。  
  
```  
BOOL m_bAutodestroyKeyframes;  
```  
  
##  <a name="a-namemlstanimationobjectsa--canimationgroupmlstanimationobjects"></a><a name="m_lstanimationobjects"></a>CAnimationGroup::m_lstAnimationObjects  
 アニメーション オブジェクトの一覧が含まれています。  
  
```  
CObList m_lstAnimationObjects;  
```  
  
##  <a name="a-namemlstkeyframesa--canimationgroupmlstkeyframes"></a><a name="m_lstkeyframes"></a>CAnimationGroup::m_lstKeyFrames  
 キーフレームの一覧が含まれています。  
  
```  
CObList m_lstKeyFrames;  
```  
  
##  <a name="a-namemngroupida--canimationgroupmngroupid"></a><a name="m_ngroupid"></a>CAnimationGroup::m_nGroupID  
 アニメーションのグループの一意の識別子。  
  
```  
UINT32 m_nGroupID;  
```  
  
##  <a name="a-namempparentcontrollera--canimationgroupmpparentcontroller"></a><a name="m_pparentcontroller"></a>CAnimationGroup::m_pParentController  
 このグループに属しているアニメーション コント ローラーへのポインター。  
  
```  
CAnimationController* m_pParentController;  
```  
  
##  <a name="a-namempstoryboarda--canimationgroupmpstoryboard"></a><a name="m_pstoryboard"></a>CAnimationGroup::m_pStoryboard  
 アニメーション ストーリー ボードへのポインター。 このポインターは、アニメーションの呼び出し後にのみ有効です。  
  
```  
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;  
```  
  
##  <a name="a-nameremovekeyframesa--canimationgroupremovekeyframes"></a><a name="removekeyframes"></a>CAnimationGroup::RemoveKeyframes  
 削除し、必要に応じてアニメーション グループに属しているすべてのキーフレームを破棄します。  
  
```  
void RemoveKeyframes();
```  
  
### <a name="remarks"></a>コメント  
 M_bAutodestroyKeyframes メンバーが TRUE の場合のキーフレームが削除され、破棄されると、それ以外の場合、キーフレームをだけキーフレームの内部の一覧から削除します。  
  
##  <a name="a-nameremovetransitionsa--canimationgroupremovetransitions"></a><a name="removetransitions"></a>CAnimationGroup::RemoveTransitions  
 アニメーション グループに属しているアニメーション オブジェクトからの遷移を削除します。  
  
```  
void RemoveTransitions();
```  
  
### <a name="remarks"></a>コメント  
 M_bAutoclearTransitions フラグが TRUE に設定されている場合、このメソッドは、グループに属しているすべてのアニメーション オブジェクトをループ処理し、CAnimationObject::ClearTransitions(FALSE) を呼び出します。  
  
##  <a name="a-nameschedulea--canimationgroupschedule"></a><a name="schedule"></a>CAnimationGroup::Schedule  
 指定された時間にアニメーションをスケジュールします。  
  
```  
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTimer`  
 アニメーション タイマーへのポインター。  
  
 `time`  
 アニメーションのスケジュールを設定する時刻を指定します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE。FALSE は、メソッドが失敗した場合、またはアニメーションの場合が呼び出されていないと bScheduleNow を FALSE に設定します。  
  
### <a name="remarks"></a>コメント  
 指定された時間にアニメーションのスケジュールを設定するには、この関数を呼び出します。 まずを FALSE に設定 bScheduleNow でアニメーションを呼び出す必要があります。  
  
##  <a name="a-namesetautodestroytransitionsa--canimationgroupsetautodestroytransitions"></a><a name="setautodestroytransitions"></a>CAnimationGroup::SetAutodestroyTransitions  
 自動的にグループに属するすべてのアニメーション オブジェクトの遷移を破棄するように指示します。  
  
```  
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bAutoDestroy`  
 遷移を破棄する方法を指定します。  
  
### <a name="remarks"></a>コメント  
 この値をスタックに遷移を割り当てる場合にのみ FALSE に設定します。 既定値は TRUE、したがってことが推奨されます新しい演算子を使用して移行オブジェクトを割り当てます。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

