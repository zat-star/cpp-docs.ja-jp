---
title: "CBaseTransition クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboardAtKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::Clear
- AFXANIMATIONCONTROLLER/CBaseTransition::Create
- AFXANIMATIONCONTROLLER/CBaseTransition::GetEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::GetStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::GetType
- AFXANIMATIONCONTROLLER/CBaseTransition::IsAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::SetKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::SetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_transition
- AFXANIMATIONCONTROLLER/CBaseTransition::m_type
dev_langs:
- C++
helpviewer_keywords:
- CBaseTransition class
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b979d03587ada42486d0462733dfe6fd22f9f7cc
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cbasetransition-class"></a>CBaseTransition クラス
基本遷移を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CBaseTransition : public CObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-enumerations"></a>パブリック列挙型  
  
|名前|説明|  
|----------|-----------------|  
|[CBaseTransition::TRANSITION_TYPE 列挙型](#transition_type_enumeration)|現在 Windows Animation API の MFC 実装によってサポートされている遷移の種類を定義します。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CBaseTransition::CBaseTransition](#cbasetransition)|切り替え効果の基本オブジェクトを構築します。|  
|[CBaseTransition:: ~ CBaseTransition](#cbasetransition__~cbasetransition)|デストラクターです。 移行オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBaseTransition::AddToStoryboard](#addtostoryboard)|ストーリー ボードに遷移を追加します。|  
|[CBaseTransition::AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|ストーリー ボードに遷移を追加します。|  
|[CBaseTransition::Clear](#clear)|リリースには、IUIAnimationTransition COM オブジェクトがカプセル化されます。|  
|[CBaseTransition::Create](#create)|COM の遷移を作成します。|  
|[CBaseTransition::GetEndKeyframe](#getendkeyframe)|返します。 は、キーフレームを起動します。|  
|[CBaseTransition::GetRelatedVariable](#getrelatedvariable)|関連する変数へのポインターを返します。|  
|[CBaseTransition::GetStartKeyframe](#getstartkeyframe)|返します。 は、キーフレームを起動します。|  
|[CBaseTransition::GetTransition](#gettransition)|オーバーロードされます。 基になる COM 遷移オブジェクトへのポインターを返します。|  
|[CBaseTransition::GetType](#gettype)|返します。 は、型を移行します。|  
|[CBaseTransition::IsAdded](#isadded)|ストーリー ボードに遷移が追加されているかどうかを指示します。|  
|[CBaseTransition::SetKeyframes](#setkeyframes)|遷移のキーフレームを設定します。|  
|[CBaseTransition::SetRelatedVariable](#setrelatedvariable)|アニメーション変数と遷移の間のリレーションシップを確立します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CBaseTransition::m_bAdded](#m_badded)|ストーリー ボードに遷移が追加されているかどうかを指定します。|  
|[CBaseTransition::m_pEndKeyframe](#m_pendkeyframe)|遷移の終わりを指定するキーフレームへのポインターを格納します。|  
|[CBaseTransition::m_pRelatedVariable](#m_prelatedvariable)|M_transition に格納されている遷移とアニメーションがアニメーション変数へのポインター。|  
|[CBaseTransition::m_pStartKeyframe](#m_pstartkeyframe)|遷移の始まりを指定するキーフレームへのポインターを格納します。|  
|[CBaseTransition::m_transition](#m_transition)|IUIAnimationTransition へのポインターを格納します。 遷移の COM オブジェクトが作成されていない場合は NULL です。|  
|[CBaseTransition::m_type](#m_type)|移行の種類を格納します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、IUIAnimationTransition インターフェイスをカプセル化し、すべての遷移の基本クラスとして機能します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CBaseTransition`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="_dtorcbasetransition"></a>CBaseTransition:: ~ CBaseTransition  
 デストラクターです。 移行オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CBaseTransition();
```  
  
##  <a name="addtostoryboard"></a>CBaseTransition::AddToStoryboard  
 ストーリー ボードに遷移を追加します。  
  
```  
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStoryboard`  
 関連する変数をアニメーション化する、ストーリー ボードへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ストーリー ボードに切り替えが正常に追加する場合は TRUE。  
  
### <a name="remarks"></a>コメント  
 ストーリー ボードに関連する変数への移行を適用します。 このストーリー ボードでこの変数に適用される最初の遷移の場合は、ストーリー ボードの開始時に、移行を開始します。 それ以外の場合、移行は、変数に最も最近追加遷移に追加されます。  
  
##  <a name="addtostoryboardatkeyframes"></a>CBaseTransition::AddToStoryboardAtKeyframes  
 ストーリー ボードに遷移を追加します。  
  
```  
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStoryboard`  
 関連する変数をアニメーション化する、ストーリー ボードへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ストーリー ボードに切り替えが正常に追加する場合は TRUE。  
  
### <a name="remarks"></a>コメント  
 ストーリー ボードに関連する変数への移行を適用します。 開始キーフレームが指定されている場合、そのキーフレームでの移行が開始されます。 移行の開始のキーフレームの開始終了キーフレームが指定されている場合、終了キーフレームが停止します。 Duration パラメーターを指定の移行が作成されている場合は、最初と最後のキーフレーム間の時間の期間でその期間が上書きされます。 キーフレームが指定されていない場合は、変数に追加されて最近移行の移行が追加されます。  
  
##  <a name="cbasetransition"></a>CBaseTransition::CBaseTransition  
 切り替え効果の基本オブジェクトを構築します。  
  
```  
CBaseTransition();
```  
  
##  <a name="clear"></a>CBaseTransition::Clear  
 リリースには、IUIAnimationTransition COM オブジェクトがカプセル化されます。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、IUITransition インターフェイスのリークを防ぐために、派生クラスの Create メソッドから呼び出す必要があります。  
  
##  <a name="create"></a>CBaseTransition::Create  
 COM の遷移を作成します。  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pLibrary`  
 標準的な遷移を作成する遷移ライブラリへのポインター。 カスタムの切り替えには、NULL になります。  
  
 `pFactory`  
 カスタム遷移を作成する遷移ファクトリへのポインター。 標準の遷移では、NULL になります。  
  
### <a name="return-value"></a>戻り値  
 遷移 COM オブジェクトが正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 これは、純粋仮想関数、派生クラスでオーバーライドする必要があります。 基になる COM 遷移オブジェクトをインスタンス化するためにフレームワークによって呼び出されます。  
  
##  <a name="getendkeyframe"></a>CBaseTransition::GetEndKeyframe  
 返します。 は、キーフレームを起動します。  
  
```  
CBaseKeyFrame* GetEndKeyframe();
```  
  
### <a name="return-value"></a>戻り値  
 キーフレーム、または NULL のキーフレームの間の遷移を挿入しないようにする場合に有効なポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、SetKeyframes で以前に設定されたキーフレーム オブジェクトへのアクセスに使用できます。 遷移は、ストーリー ボードに追加されている場合は、最上位のコードによって呼び出されます。  
  
##  <a name="getrelatedvariable"></a>CBaseTransition::GetRelatedVariable  
 関連する変数へのポインターを返します。  
  
```  
CAnimationVariable* GetRelatedVariable();
```  
  
### <a name="return-value"></a>戻り値  
 アニメーション変数、または NULL SetRelatedVariable によってアニメーション変数が設定されていない場合に有効なポインター。  
  
### <a name="remarks"></a>コメント  
 これは、関連するアニメーション変数にアクセサーです。  
  
##  <a name="getstartkeyframe"></a>CBaseTransition::GetStartKeyframe  
 返します。 は、キーフレームを起動します。  
  
```  
CBaseKeyFrame* GetStartKeyframe();
```  
  
### <a name="return-value"></a>戻り値  
 キーフレームをまたはキーフレームの後の移行が開始しないようにする場合は NULL に有効なポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、SetKeyframes で以前に設定されたキーフレーム オブジェクトへのアクセスに使用できます。 遷移は、ストーリー ボードに追加されている場合は、最上位のコードによって呼び出されます。  
  
##  <a name="gettransition"></a>CBaseTransition::GetTransition  
 基になる COM 遷移オブジェクトへのポインターを返します。  
  
```  
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory);  
  
IUIAnimationTransition* GetTransition();
```  
  
### <a name="parameters"></a>パラメーター  
 `pLibrary`  
 標準的な遷移を作成する遷移ライブラリへのポインター。 カスタムの切り替えには、NULL になります。  
  
 `pFactory`  
 カスタム遷移を作成する遷移ファクトリへのポインター。 標準の遷移では、NULL になります。  
  
### <a name="return-value"></a>戻り値  
 IUIAnimationTransition または遷移の基になる場合は NULL に有効なポインターを作成できません。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、基になる COM 遷移オブジェクトへのポインターを返し、必要な場合は作成されます。  
  
##  <a name="gettype"></a>CBaseTransition::GetType  
 返します。 は、型を移行します。  
  
```  
TRANSITION_TYPE GetType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 TRANSITION_TYPE のいずれかの列挙値です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、型によって遷移オブジェクトを識別するために使用できます。 種類は、派生クラスでコンス トラクターで設定されます。  
  
##  <a name="isadded"></a>CBaseTransition::IsAdded  
 ストーリー ボードに遷移が追加されているかどうかを指示します。  
  
```  
BOOL IsAdded();
```  
  
### <a name="return-value"></a>戻り値  
 遷移が FALSE の場合は、ストーリー ボードに追加されたかどうかに TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグは、最上位レベルのコードは、ストーリー ボードへの切り替えを追加するときに、内部的に設定されます。  
  
##  <a name="m_badded"></a>CBaseTransition::m_bAdded  
 ストーリー ボードに遷移が追加されているかどうかを指定します。  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="m_pendkeyframe"></a>CBaseTransition::m_pEndKeyframe  
 遷移の終わりを指定するキーフレームへのポインターを格納します。  
  
```  
CBaseKeyFrame* m_pEndKeyframe;  
```  
  
##  <a name="m_prelatedvariable"></a>CBaseTransition::m_pRelatedVariable  
 M_transition に格納されている遷移とアニメーションがアニメーション変数へのポインター。  
  
```  
CAnimationVariable* m_pRelatedVariable;  
```  
  
##  <a name="m_pstartkeyframe"></a>CBaseTransition::m_pStartKeyframe  
 遷移の始まりを指定するキーフレームへのポインターを格納します。  
  
```  
CBaseKeyFrame* m_pStartKeyframe;  
```  
  
##  <a name="m_transition"></a>CBaseTransition::m_transition  
 IUIAnimationTransition へのポインターを格納します。 遷移の COM オブジェクトが作成されていない場合は NULL です。  
  
```  
ATL::CComPtr<IUIAnimationTransition> m_transition;  
```  
  
##  <a name="m_type"></a>CBaseTransition::m_type  
 移行の種類を格納します。  
  
```  
TRANSITION_TYPE m_type;  
```  
  
##  <a name="setkeyframes"></a>CBaseTransition::SetKeyframes  
 遷移のキーフレームを設定します。  
  
```  
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,  
    CBaseKeyFrame* pEnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStart`  
 遷移の始まりを指定するキーフレームです。  
  
 `pEnd`  
 遷移の終わりを指定するキーフレームです。  
  
### <a name="remarks"></a>コメント  
 この方法で指定したキーフレームの後に起動し、保留が NULL でない場合は終了必要に応じて、遷移は、指定したキーフレームの前にします。 Duration パラメーターを指定の移行が作成されている場合は、最初と最後のキーフレーム間の時間の期間でその期間が上書きされます。  
  
##  <a name="setrelatedvariable"></a>CBaseTransition::SetRelatedVariable  
 アニメーション変数と遷移の間のリレーションシップを確立します。  
  
```  
void SetRelatedVariable(CAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>パラメーター  
 `pVariable`  
 関連するアニメーション変数へのポインター。  
  
### <a name="remarks"></a>コメント  
 アニメーション変数と遷移の間のリレーションシップを確立します。 遷移は、1 つの変数にのみ適用できます。  
  
##  <a name="transition_type_enumeration"></a>CBaseTransition::TRANSITION_TYPE 列挙型  
 現在 Windows Animation API の MFC 実装によってサポートされている遷移の種類を定義します。  
  
```  
enum TRANSITION_TYPE;  
```  
  
### <a name="remarks"></a>コメント  
 移行の種類は、特定の遷移のコンス トラクターで設定されます。 たとえば、CSinusoidalTransitionFromRange は、その型を SINUSOIDAL_FROM_RANGE に設定します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

