---
title: "CAnimationVariable クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationVariable::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::Create
- AFXANIMATIONCONTROLLER/CAnimationVariable::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_dblDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_lstTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_pParentObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_variable
dev_langs:
- C++
helpviewer_keywords:
- CAnimationVariable class
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
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
ms.openlocfilehash: 42513c841f6dc891369d7d6640ced1aa37f90e8e
ms.lasthandoff: 02/24/2017

---
# <a name="canimationvariable-class"></a>CAnimationVariable クラス
アニメーション変数を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationVariable;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationVariable::CAnimationVariable](#canimationvariable)|アニメーション変数のオブジェクトを構築します。|  
|[CAnimationVariable:: ~ CAnimationVariable](#canimationvariable__~canimationvariable)|デストラクターです。 CAnimationVariable のオブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationVariable::AddTransition](#addtransition)|遷移を追加します。|  
|[CAnimationVariable::ApplyTransitions](#applytransitions)|ストーリー ボードを内部リストから、遷移を追加します。|  
|[CAnimationVariable::ClearTransitions](#cleartransitions)|遷移をクリアします。|  
|[CAnimationVariable::Create](#create)|基になるアニメーション変数 COM オブジェクトを作成します。|  
|[CAnimationVariable::CreateTransitions](#createtransitions)|このアニメーション変数に適用されるすべての遷移を作成します。|  
|[CAnimationVariable::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|有効または IntegerValueChanged イベントを無効にします。|  
|[CAnimationVariable::EnableValueChangedEvent](#enablevaluechangedevent)|有効または ValueChanged イベントを無効にします。|  
|[CAnimationVariable::GetDefaultValue](#getdefaultvalue)|既定値を返します。|  
|[CAnimationVariable::GetParentAnimationObject](#getparentanimationobject)|親を返しますアニメーション オブジェクトです。|  
|[CAnimationVariable::GetValue](#getvalue)|オーバーロードされます。 アニメーション変数の現在の値を返します。|  
|[CAnimationVariable::GetVariable](#getvariable)|IUIAnimationVariable COM オブジェクトへのポインターを返します。|  
|[CAnimationVariable::SetDefaultValue](#setdefaultvalue)|既定値を設定し、IUIAnimationVariable COM オブジェクトを解放します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationVariable::SetParentAnimationObject](#setparentanimationobject)|アニメーション変数と、アニメーション オブジェクト間のリレーションシップを設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationVariable::m_bAutodestroyTransitions](#m_bautodestroytransitions)|関連の transition オブジェクトを削除するかどうかを指定します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationVariable::m_dblDefaultValue](#m_dbldefaultvalue)|IUIAnimationVariable に伝達は、既定値を指定します。|  
|[CAnimationVariable::m_lstTransitions](#m_lsttransitions)|このアニメーション変数をアニメーション化する遷移の一覧が含まれています。|  
|[CAnimationVariable::m_pParentObject](#m_pparentobject)|このアニメーション変数をカプセル化するアニメーション オブジェクトへのポインター。|  
|[CAnimationVariable::m_variable](#m_variable)|IUIAnimationVariable COM オブジェクトへのポインターを格納します。 COM オブジェクトは、まだ作成されていない場合、または作成が失敗した場合は NULL です。|  
  
## <a name="remarks"></a>コメント  
 CAnimationVariable クラスは、IUIAnimationVariable COM オブジェクトをカプセル化します。 ストーリー ボードでアニメーション変数に適用する遷移の一覧も保持します。 CAnimationVariable オブジェクトは、アプリケーションのアニメーション化された値、ポイント、サイズ、色、および四角形で表すことができます、アニメーション オブジェクトに埋め込まれています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CAnimationVariable`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationvariable"></a>CAnimationVariable:: ~ CAnimationVariable  
 デストラクターです。 CAnimationVariable のオブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CAnimationVariable();
```  
  
##  <a name="addtransition"></a>CAnimationVariable::AddTransition  
 遷移を追加します。  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTransition`  
 追加への移行へのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは切り替え効果のアニメーション変数に適用する遷移の内部リストに追加します。 アニメーションがスケジュールされているときに、この一覧をクリアする必要があります。  
  
##  <a name="applytransitions"></a>CAnimationVariable::ApplyTransitions  
 ストーリー ボードを内部リストから、遷移を追加します。  
  
```  
void ApplyTransitions(
    CAnimationController* pController,  
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>パラメーター  
 `pController`  
 親アニメーション コント ローラーへのポインター。  
  
 `pStoryboard`  
 ストーリー ボードへのポインター。  
  
 `bDependOnKeyframes`  
 TRUE をこのメソッドは、キーフレームに依存する切り替えを追加する必要があります。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ストーリー ボードを内部リストから、遷移を追加します。 呼び出されます最上位レベルのコードから複数回のキーフレームに依存をキーフレームに依存する切り替え効果を追加しない遷移を追加します。 基になるアニメーション変数の COM オブジェクトが作成されていない場合、このメソッドをこの段階で作成します。  
  
##  <a name="canimationvariable"></a>CAnimationVariable::CAnimationVariable  
 アニメーション変数のオブジェクトを構築します。  
  
```  
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```  
  
### <a name="parameters"></a>パラメーター  
 `dblDefaultValue`  
 既定値を指定します。  
  
### <a name="remarks"></a>コメント  
 アニメーション変数のオブジェクトを構築し、その既定値を設定します。 既定値は、変数がアニメーション化しないか、またはアニメーション化することはできませんとに使用されます。  
  
##  <a name="cleartransitions"></a>CAnimationVariable::ClearTransitions  
 遷移をクリアします。  
  
```  
void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>パラメーター  
 `bAutodestroy`  
 このメソッドが transition オブジェクトを削除するかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、すべての遷移を遷移の内部の一覧から削除します。 BAutodestroy が true の場合、または、m_bAutodestroyTransitions が TRUE の場合、遷移は削除されます。 それ以外の場合、呼び出し元は、transition オブジェクトを解放する必要があります。  
  
##  <a name="create"></a>CAnimationVariable::Create  
 基になるアニメーション変数 COM オブジェクトを作成します。  
  
```  
virtual BOOL Create(IUIAnimationManager* pManager);
```  
  
### <a name="parameters"></a>パラメーター  
 `pManager`  
 アニメーション マネージャーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 アニメーション変数が作成された場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、基になるアニメーション変数の COM オブジェクトを作成し、その既定値を設定します。  
  
##  <a name="createtransitions"></a>CAnimationVariable::CreateTransitions  
 このアニメーション変数に適用されるすべての遷移を作成します。  
  
```  
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>パラメーター  
`pLibrary`  
 ポインター、 [IUIAnimationTransitionLibrary インターフェイス](https://msdn.microsoft.com/library/windows/desktop/dd371897)、標準の遷移のライブラリを定義します。  
  
### <a name="return-value"></a>戻り値  
 移行が正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 遷移の変数の内部リストに追加された遷移を作成する必要があるときに、このメソッドはフレームワークによって呼び出されます。  
  
##  <a name="enableintegervaluechangedevent"></a>CAnimationVariable::EnableIntegerValueChangedEvent  
 有効または IntegerValueChanged イベントを無効にします。  
  
```  
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 `pController`  
 親コント ローラーへのポインター。  
  
 `bEnable`  
 TRUE - 有効にするイベントを FALSE には、イベントを無効にします。  
  
### <a name="remarks"></a>コメント  
 ValueChanged イベントが有効にすると、フレームワークは CAnimationController::OnAnimationIntegerValueChanged の仮想メソッドを呼び出します。 このイベントを処理するために CAnimationController から派生したクラスでオーバーライドする必要があります。 アニメーション変数の整数値が変更されるたびに、このメソッドが呼び出されます。  
  
##  <a name="enablevaluechangedevent"></a>CAnimationVariable::EnableValueChangedEvent  
 有効または ValueChanged イベントを無効にします。  
  
```  
void EnableValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 `pController`  
 親コント ローラーへのポインター。  
  
 `bEnable`  
 TRUE - 有効にするイベントを FALSE には、イベントを無効にします。  
  
### <a name="remarks"></a>コメント  
 ValueChanged イベントが有効にすると、フレームワークは CAnimationController::OnAnimationValueChanged の仮想メソッドを呼び出します。 このイベントを処理するために CAnimationController から派生したクラスでオーバーライドする必要があります。 アニメーション変数の値が変更されるたびに、このメソッドが呼び出されます。  
  
##  <a name="getdefaultvalue"></a>CAnimationVariable::GetDefaultValue  
 既定値を返します。  
  
```  
DOUBLE GetDefaultValue() const;  
```  
  
### <a name="return-value"></a>戻り値  
 既定値。  
  
### <a name="remarks"></a>コメント  
 この関数を使用すると、アニメーション変数の既定値を取得できます。 コンス トラクターまたは SetDefaultValue メソッドによって、既定値を設定できます。  
  
##  <a name="getparentanimationobject"></a>CAnimationVariable::GetParentAnimationObject  
 親を返しますアニメーション オブジェクトです。  
  
```  
CAnimationBaseObject* GetParentAnimationObject();
```  
  
### <a name="return-value"></a>戻り値  
 それ以外の場合のリレーションシップが確立された場合に、親アニメーション オブジェクトへのポインターが NULL です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出して親アニメーション オブジェクト (コンテナー) へのポインターを取得します。  
  
##  <a name="getvalue"></a>CAnimationVariable::GetValue  
 アニメーション変数の現在の値を返します。  
  
```  
HRESULT GetValue(DOUBLE& dblValue);  
HRESULT GetValue(INT32& nValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `dblValue`  
 アニメーション変数の現在の値。  
  
 `nValue`  
 アニメーション変数の現在の値。  
  
### <a name="return-value"></a>戻り値  
 値が正常に取得されたか、基になるアニメーション変数が作成されていない場合は S_OK です。 それ以外の場合の HRESULT エラー コード。  
  
### <a name="remarks"></a>コメント  
 アニメーション変数の現在の値を取得するこのメソッドを呼び出すことができます。 基になる COM オブジェクトが作成されていない場合 dblValue で関数が戻るときに既定値が格納されます。  
  
##  <a name="getvariable"></a>CAnimationVariable::GetVariable  
 IUIAnimationVariable COM オブジェクトへのポインターを返します。  
  
```  
IUIAnimationVariable* GetVariable();
```  
  
### <a name="return-value"></a>戻り値  
 IUIAnimationVariable COM オブジェクト、または NULL アニメーション変数作成されていない、または作成できない場合に有効なポインター。  
  
### <a name="remarks"></a>コメント  
 基になる IUIAnimationVariable COM オブジェクトにアクセスし、必要な場合は、そのメソッドを直接呼び出すには、この関数を使用します。  
  
##  <a name="m_bautodestroytransitions"></a>CAnimationVariable::m_bAutodestroyTransitions  
 関連の transition オブジェクトを削除するかどうかを指定します。  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
### <a name="remarks"></a>コメント  
 遷移の内部の一覧から削除されている場合は、transition オブジェクトの削除を強制する場合は true には、この値を設定します。 この値が FALSE の場合は、アプリケーションを呼び出すことで、切り替え効果を削除してください。 常に、遷移の一覧をオフするは、アニメーションがスケジュールされているになります。 既定値は FALSE です。  
  
##  <a name="m_dbldefaultvalue"></a>CAnimationVariable::m_dblDefaultValue  
 IUIAnimationVariable に伝達は、既定値を指定します。  
  
```  
DOUBLE m_dblDefaultValue;  
```  
  
##  <a name="m_lsttransitions"></a>CAnimationVariable::m_lstTransitions  
 このアニメーション変数をアニメーション化する遷移の一覧が含まれています。  
  
```  
CObList m_lstTransitions;  
```  
  
##  <a name="m_pparentobject"></a>CAnimationVariable::m_pParentObject  
 このアニメーション変数をカプセル化するアニメーション オブジェクトへのポインター。  
  
```  
CAnimationBaseObject* m_pParentObject;  
```  
  
##  <a name="m_variable"></a>CAnimationVariable::m_variable  
 IUIAnimationVariable COM オブジェクトへのポインターを格納します。 COM オブジェクトは、まだ作成されていない場合、または作成が失敗した場合は NULL です。  
  
```  
ATL::CComPtr<IUIAnimationVariable> m_variable;  
```  
  
##  <a name="setdefaultvalue"></a>CAnimationVariable::SetDefaultValue  
 既定値を設定し、IUIAnimationVariable COM オブジェクトを解放します。  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `dblDefaultValue`  
 新しい既定値を指定します。  
  
### <a name="remarks"></a>コメント  
 既定値にリセットするのにには、このメソッドを使用します。 このメソッドは、解放内部 IUIAnimationVariable COM オブジェクト、したがってアニメーション変数を再作成される、基になる COM オブジェクトは、新しい既定値を取得します。 アニメーション変数を表す COM オブジェクトを作成していない場合、または変数がアニメーション化されていない場合、GetValue によって既定値が返されます。  
  
##  <a name="setparentanimationobject"></a>CAnimationVariable::SetParentAnimationObject  
 アニメーション変数と、アニメーション オブジェクト間のリレーションシップを設定します。  
  
```  
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentObject`  
 この変数を格納しているアニメーション オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、アニメーション変数とそれをカプセル化するアニメーション オブジェクトの間の一対一のリレーションシップを確立するために内部的に呼び出されます。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

