---
title: "CAnimationBaseObject クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CAnimationBaseObject
- CAnimationBaseObject
dev_langs:
- C++
helpviewer_keywords:
- CAnimationBaseObject class
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
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
ms.openlocfilehash: c714c78b7017ed314b30f64df4bfceb587226c15
ms.lasthandoff: 02/24/2017

---
# <a name="canimationbaseobject-class"></a>CAnimationBaseObject クラス
すべてのアニメーション オブジェクトの基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationBaseObject : public CObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationBaseObject::CAnimationBaseObject](#canimationbaseobject)|オーバーロードされます。 アニメーション オブジェクトを構築します。|  
|[CAnimationBaseObject:: ~ CAnimationBaseObject](#canimationbaseobject__~canimationbaseobject)|デストラクターです。 アニメーション オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationBaseObject::ApplyTransitions](#applytransitions)|カプセル化されたアニメーション変数を持つストーリー ボードへの切り替えを追加します。|  
|[CAnimationBaseObject::ClearTransitions](#cleartransitions)|関連するすべての遷移を削除します。|  
|[CAnimationBaseObject::ContainsVariable](#containsvariable)|アニメーション オブジェクトに特定のアニメーション変数が含まれているかどうかを判断します。|  
|[CAnimationBaseObject::CreateTransitions](#createtransitions)|アニメーション オブジェクトに関連付けられている遷移を作成します。|  
|[CAnimationBaseObject::DetachFromController](#detachfromcontroller)|親アニメーション コント ローラーからアニメーション オブジェクトをデタッチします。|  
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|整数値の変更イベント ハンドラーを設定します。|  
|[CAnimationBaseObject::EnableValueChangedEvent](#enablevaluechangedevent)|イベント ハンドラーの値が変更を設定します。|  
|[CAnimationBaseObject::GetAutodestroyTransitions](#getautodestroytransitions)|関連する遷移が自動的に破棄されるかどうかを指示します。|  
|[CAnimationBaseObject::GetGroupID](#getgroupid)|現在のグループ ID を返します。|  
|[CAnimationBaseObject::GetObjectID](#getobjectid)|現在のオブジェクト ID を返します。|  
|[CAnimationBaseObject::GetUserData](#getuserdata)|ユーザー定義データを返します。|  
|[CAnimationBaseObject::SetAutodestroyTransitions](#setautodestroytransitions)|切り替え効果を自動的に破棄する順序付けをするフラグを設定します。|  
|[CAnimationBaseObject::SetID](#setid)|新しい Id を設定します。|  
|[CAnimationBaseObject::SetUserData](#setuserdata)|ユーザー定義データを設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationBaseObject::GetAnimationVariableList](#getanimationvariablelist)|含まれているアニメーション変数へのポインターを収集します。|  
|[CAnimationBaseObject::SetParentAnimationObjects](#setparentanimationobjects)|アニメーション オブジェクト、およびそのコンテナーに含まれるアニメーション変数間の関係を確立します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationBaseObject::m_bAutodestroyTransitions](#m_bautodestroytransitions)|関連する遷移が自動的に破棄される必要があるかどうかを指定します。|  
|[CAnimationBaseObject::m_dwUserData](#m_dwuserdata)|ユーザー定義データを格納します。|  
|[CAnimationBaseObject::m_nGroupID](#m_ngroupid)|アニメーション オブジェクトのグループ ID を指定します。|  
|[CAnimationBaseObject::m_nObjectID](#m_nobjectid)|アニメーション オブジェクトのオブジェクト ID を指定します。|  
|[CAnimationBaseObject::m_pParentController](#m_pparentcontroller)|親アニメーション コント ローラーへのポインター。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、すべてのアニメーション オブジェクトの基本のメソッドを実装します。 アニメーション オブジェクトでは、値、ポイント、サイズ、四角形を表すしたり、任意のカスタム エンティティと同様に、アプリケーションで色をすることができます。 アニメーション オブジェクトは、アニメーションのグループ (CAnimationGroup を参照してください) に格納されます。 各グループとは別にアニメーション化できるし、ストーリー ボードの類似性として扱うことができます。 アニメーション オブジェクトでは、1 つまたは複数のアニメーション変数 (CAnimationVariable を参照してください) の論理表現によってカプセル化します。 たとえば、CAnimationRect には、次の&4; つのアニメーション変数四角形の各辺に&1; つの変数にはが含まれています。 各アニメーション オブジェクト クラスでは、遷移をカプセル化されたアニメーション変数に適用するために使用するオーバー ロードの AddTransition メソッドを公開します。 アニメーション オブジェクトはオブジェクト ID を使用して (必要に応じて)、グループ id。 グループ ID は、適切なグループに、アニメーション オブジェクトを配置するために必要ですが、オブジェクトが、ID が 0 の既定のグループに配置されるグループ ID が指定されていない場合。 を呼び出した場合、さまざまな GroupID で SetID アニメーション オブジェクトを別のグループ (新しいグループは、必要な場合に作成されます) に移動されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAnimationBaseObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="a-namedtorcanimationbaseobjecta--canimationbaseobjectcanimationbaseobject"></a><a name="_dtorcanimationbaseobject"></a>CAnimationBaseObject:: ~ CAnimationBaseObject  
 デストラクターです。 アニメーション オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CAnimationBaseObject();
```  
  
##  <a name="a-nameapplytransitionsa--canimationbaseobjectapplytransitions"></a><a name="applytransitions"></a>CAnimationBaseObject::ApplyTransitions  
 カプセル化されたアニメーション変数を持つストーリー ボードへの切り替えを追加します。  
  
```  
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStoryboard`  
 ストーリー ボードへのポインター。  
  
 `bDependOnKeyframes`  
 False は、このメソッドは、キーフレームに依存しない遷移のみを追加します。  
  
### <a name="return-value"></a>戻り値  
 移行が正常に追加された場合は TRUE。  
  
### <a name="remarks"></a>コメント  
 ストーリー ボードを AddTransition (派生クラスではオーバー ロードされたメソッド) に追加されている関連する遷移を追加します。  
  
##  <a name="a-namecanimationbaseobjecta--canimationbaseobjectcanimationbaseobject"></a><a name="canimationbaseobject"></a>CAnimationBaseObject::CAnimationBaseObject  
 アニメーション オブジェクトを構築します。  
  
```  
CAnimationBaseObject();

 
CAnimationBaseObject(
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nGroupID`  
 グループ ID を指定します  
  
 `nObjectID`  
 オブジェクト ID を指定します  
  
 `dwUserData`  
 ユーザー定義のデータのアニメーション オブジェクトに関連付けられている、実行時に後で取得できます。  
  
### <a name="remarks"></a>コメント  
 アニメーション オブジェクトを構築し、既定のオブジェクト ID (0) およびグループ ID (0) を割り当てます。  
  
##  <a name="a-namecleartransitionsa--canimationbaseobjectcleartransitions"></a><a name="cleartransitions"></a>CAnimationBaseObject::ClearTransitions  
 関連するすべての遷移を削除します。  
  
```  
virtual void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>パラメーター  
 `bAutodestroy`  
 自動的には、transition オブジェクトを破棄またはだけ関連一覧から削除するかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 関連するすべての遷移を削除し、bAutodestroy または m_bAutodestroyTransitions フラグが TRUE の場合は、それらを破棄します。 遷移は、スタックに割り当てられるいない場合にのみ、自動的に破棄する必要があります。 上記のフラグが FALSE の場合は、遷移のみ関連する遷移の内部の一覧から削除されます。  
  
##  <a name="a-namecontainsvariablea--canimationbaseobjectcontainsvariable"></a><a name="containsvariable"></a>CAnimationBaseObject::ContainsVariable  
 アニメーション オブジェクトに特定のアニメーション変数が含まれているかどうかを判断します。  
  
```  
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>パラメーター  
 `pVariable`  
 アニメーション変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 アニメーション オブジェクトのアニメーション変数を格納している場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 アニメーション オブジェクト内で pVariable で指定されたアニメーション変数が含まれているかどうかを判断するこのメソッドを使用できます。 アニメーション オブジェクトの種類によっては、いくつかのアニメーション変数を含めることができます。 たとえば、CAnimationColor には、各色成分 (赤、緑、および青) のいずれかの&3; つの変数が含まれています。 アニメーション変数の値が変更されたときに、Windows Animation API は ValueChanged または IntegerValueChanged イベント (有効な場合)、および、このイベントのパラメーターは、インターフェイスのアニメーション変数 IUIAnimationVariable へのポインターを送信します。 このメソッドは、格納されている COM オブジェクトへのポインターからアニメーションへのポインターを取得するのに役立ちます。  
  
##  <a name="a-namecreatetransitionsa--canimationbaseobjectcreatetransitions"></a><a name="createtransitions"></a>CAnimationBaseObject::CreateTransitions  
 アニメーション オブジェクトに関連付けられている遷移を作成します。  
  
```  
BOOL CreateTransitions();
```  
  
### <a name="return-value"></a>戻り値  
 移行が正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 派生のアニメーション オブジェクトにカプセル化、アニメーション変数の一覧をループ処理し、各アニメーション変数に関連付けられている遷移を作成します。  
  
##  <a name="a-namedetachfromcontrollera--canimationbaseobjectdetachfromcontroller"></a><a name="detachfromcontroller"></a>CAnimationBaseObject::DetachFromController  
 親アニメーション コント ローラーからアニメーション オブジェクトをデタッチします。  
  
```  
void DetachFromController();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは内部的に使用されます。  
  
##  <a name="a-nameenableintegervaluechangedeventa--canimationbaseobjectenableintegervaluechangedevent"></a><a name="enableintegervaluechangedevent"></a>CAnimationBaseObject::EnableIntegerValueChangedEvent  
 整数値の変更イベント ハンドラーを設定します。  
  
```  
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 `pController`  
 親のコント ローラーへのポインター。  
  
 `bEnable`  
 有効化、または整数値の変更イベントを無効にするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 整数値の変更イベント ハンドラーが有効になっている場合は、CAnimationController から派生したクラスでオーバーライドする必要があります CAnimationController::OnAnimationIntegerValueChanged メソッドでは、このイベントを処理できます。 アニメーションの整数値が変更されるたびに、このメソッドが呼び出されます。  
  
##  <a name="a-nameenablevaluechangedeventa--canimationbaseobjectenablevaluechangedevent"></a><a name="enablevaluechangedevent"></a>CAnimationBaseObject::EnableValueChangedEvent  
 イベント ハンドラーの値が変更を設定します。  
  
```  
virtual void EnableValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 `pController`  
 親のコント ローラーへのポインター。  
  
 `bEnable`  
 有効化、または値の変更イベントを無効にするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 値が変更イベント ハンドラーが有効になっている場合は、CAnimationController から派生したクラスでオーバーライドする必要があります CAnimationController::OnAnimationValueChanged メソッドでは、このイベントを処理できます。 アニメーションの値が変更されるたびに、このメソッドが呼び出されます。  
  
##  <a name="a-namegetanimationvariablelista--canimationbaseobjectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationBaseObject::GetAnimationVariableList  
 含まれているアニメーション変数へのポインターを収集します。  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lst`  
 アニメーション オブジェクトに含まれるアニメーション変数を代入するリスト。  
  
### <a name="remarks"></a>コメント  
 これは純粋仮想メソッドを派生クラスでオーバーライドされる必要があります。 その型に依存するアニメーション オブジェクトには、1 つまたは複数のアニメーション変数が含まれています。 たとえば、CAnimationPoint には X と Y 座標をそれぞれの&2; つの変数が含まれます。 基本クラス CAnimationBaseObject によってジェネリック メソッドでアニメーション変数の一覧の機能を実装する: ApplyTransitions、ClearTransitions、EnableValueChangedEvent、EnableIntegerValueChangedEvent です。 これらのメソッドは GetAnimationVariableList で、特定のアニメーション オブジェクトに含まれる実際のアニメーション変数が派生クラスに入力されますを呼び出して一覧をループし、必要なアクションを実行します。 カスタム アニメーション オブジェクトを作成する場合は、そのオブジェクトに含まれるすべてのアニメーション変数を lst に追加する必要があります。  
  
##  <a name="a-namegetautodestroytransitionsa--canimationbaseobjectgetautodestroytransitions"></a><a name="getautodestroytransitions"></a>CAnimationBaseObject::GetAutodestroyTransitions  
 関連する遷移が自動的に破棄されるかどうかを指示します。  
  
```  
BOOL GetAutodestroyTransitions() const;  
```  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、関連する遷移を自動的に破棄します。FALSE の場合、transition オブジェクトにアプリケーションを呼び出すことによって割り当てを解除する必要があります。  
  
### <a name="remarks"></a>コメント  
 既定ではこのフラグは TRUE です。 スタック上のトランジションの割り当てや、呼び出し元のアプリケーションによって解放されることは遷移している場合にのみ、このフラグを設定します。  
  
##  <a name="a-namegetgroupida--canimationbaseobjectgetgroupid"></a><a name="getgroupid"></a>CAnimationBaseObject::GetGroupID  
 現在のグループ ID を返します。  
  
```  
UINT32 GetGroupID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のグループ id。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、グループ ID を取得 グループ ID が設定されていない明示的にコンス トラクターや SetID の場合は 0 のです。  
  
##  <a name="a-namegetobjectida--canimationbaseobjectgetobjectid"></a><a name="getobjectid"></a>CAnimationBaseObject::GetObjectID  
 現在のオブジェクト ID を返します。  
  
```  
UINT32 GetObjectID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のオブジェクト id。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、オブジェクト ID を取得 それはのオブジェクト ID が設定されていない場合に明示的にコンス トラクターや SetID に 0 です。  
  
##  <a name="a-namegetuserdataa--canimationbaseobjectgetuserdata"></a><a name="getuserdata"></a>CAnimationBaseObject::GetUserData  
 ユーザー定義データを返します。  
  
```  
DWORD GetUserData() const;  
```  
  
### <a name="return-value"></a>戻り値  
 カスタム データの値。  
  
### <a name="remarks"></a>コメント  
 実行時にカスタム データを取得するには、このメソッドを呼び出します。 明示的にコンス トラクター、または SetUserData で初期化されていたいない場合は、返される値を 0 になります。  
  
##  <a name="a-namembautodestroytransitionsa--canimationbaseobjectmbautodestroytransitions"></a><a name="m_bautodestroytransitions"></a>CAnimationBaseObject::m_bAutodestroyTransitions  
 関連する遷移が自動的に破棄される必要があるかどうかを指定します。  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
##  <a name="a-namemdwuserdataa--canimationbaseobjectmdwuserdata"></a><a name="m_dwuserdata"></a>CAnimationBaseObject::m_dwUserData  
 ユーザー定義データを格納します。  
  
```  
DWORD m_dwUserData;  
```  
  
##  <a name="a-namemngroupida--canimationbaseobjectmngroupid"></a><a name="m_ngroupid"></a>CAnimationBaseObject::m_nGroupID  
 アニメーション オブジェクトのグループ ID を指定します。  
  
```  
UINT32 m_nGroupID;  
```  
  
##  <a name="a-namemnobjectida--canimationbaseobjectmnobjectid"></a><a name="m_nobjectid"></a>CAnimationBaseObject::m_nObjectID  
 アニメーション オブジェクトのオブジェクト ID を指定します。  
  
```  
UINT32 m_nObjectID;  
```  
  
##  <a name="a-namempparentcontrollera--canimationbaseobjectmpparentcontroller"></a><a name="m_pparentcontroller"></a>CAnimationBaseObject::m_pParentController  
 親アニメーション コント ローラーへのポインター。  
  
```  
CAnimationController* m_pParentController;  
```  
  
##  <a name="a-namesetautodestroytransitionsa--canimationbaseobjectsetautodestroytransitions"></a><a name="setautodestroytransitions"></a>CAnimationBaseObject::SetAutodestroyTransitions  
 切り替え効果を自動的に破棄する順序付けをするフラグを設定します。  
  
```  
void SetAutodestroyTransitions(BOOL bValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `bValue`  
 自動破棄フラグを指定します。  
  
### <a name="remarks"></a>コメント  
 新しい演算子を使用して transition オブジェクトが割り当てられている場合にのみ、このフラグを設定します。 自動の破棄 transition オブジェクトは、スタックに割り当てられたいくつかの理由から、フラグが FALSE にする必要があります。 既定ではこのフラグは TRUE です。  
  
##  <a name="a-namesetida--canimationbaseobjectsetid"></a><a name="setid"></a>CAnimationBaseObject::SetID  
 新しい Id を設定します。  
  
```  
void SetID(
    UINT32 nObjectID,  
    UINT32 nGroupID = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nObjectID`  
 新しいオブジェクトの ID を指定します  
  
 `nGroupID`  
 新しいグループの ID を指定します  
  
### <a name="remarks"></a>コメント  
 オブジェクト ID およびグループ ID を変更するのには、します。 新しいグループの ID と異なる場合、現在の ID、アニメーション オブジェクトは、もう&1; つ (新しいグループを作成するグループ、必要な場合) に移動されます。  
  
##  <a name="a-namesetparentanimationobjectsa--canimationbaseobjectsetparentanimationobjects"></a><a name="setparentanimationobjects"></a>CAnimationBaseObject::SetParentAnimationObjects  
 アニメーション オブジェクト、およびそのコンテナーに含まれるアニメーション変数間の関係を確立します。  
  
```  
virtual void SetParentAnimationObjects();
```  
  
### <a name="remarks"></a>コメント  
 これは、アニメーション オブジェクト、およびそのコンテナーに含まれるアニメーション変数間の関係を確立するために使用できるヘルパーです。 アニメーション変数をループ処理し、バック ポインター アニメーションに親オブジェクトをアニメーションの各変数に設定します。 CAnimationBaseObject::ApplyTransitions で実際の関係が確立された現在の実装ではこのため戻りポインターが設定されていない CAnimationGroup::Animate を呼び出すまでです。 関係を知っておく役に立つ CAnimationVariable (CAnimationVariable::GetParentAnimationObject を使用して) からオブジェクトのイベントと親のアニメーションを取得する必要が処理したとします。  
  
##  <a name="a-namesetuserdataa--canimationbaseobjectsetuserdata"></a><a name="setuserdata"></a>CAnimationBaseObject::SetUserData  
 ユーザー定義データを設定します。  
  
```  
void SetUserData (DWORD dwUserData);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwUserData`  
 カスタム データを指定します。  
  
### <a name="remarks"></a>コメント  
 アニメーション オブジェクトにカスタム データを関連付けるには、このメソッドを使用します。 このデータが後で取得する実行時に GetUserData でします。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

