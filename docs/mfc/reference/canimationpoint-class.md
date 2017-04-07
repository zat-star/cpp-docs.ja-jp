---
title: "CAnimationPoint クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetX
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetY
- AFXANIMATIONCONTROLLER/CAnimationPoint::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_xValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_yValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationPoint class
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: a6a59ad85928c199a8dd911b915076ffbd0b0e37
ms.lasthandoff: 02/24/2017

---
# <a name="canimationpoint-class"></a>CAnimationPoint クラス
座標をアニメーション化できる点の機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationPoint : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationPoint::CAnimationPoint](#canimationpoint)|オーバーロードされます。 CAnimationPoint オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationPoint::AddTransition](#addtransition)|X の遷移を追加し、Y 座標。|  
|[CAnimationPoint::GetDefaultValue](#getdefaultvalue)|X の既定値を返す座標と Y 座標。|  
|[CAnimationPoint::GetValue](#getvalue)|現在の値を返します。|  
|[CAnimationPoint::GetX](#getx)|X 座標の CAnimationVariable へのアクセスを提供します。|  
|[CAnimationPoint::GetY](#gety)|Y 座標の CAnimationVariable へのアクセスを提供します。|  
|[CAnimationPoint::SetDefaultValue](#setdefaultvalue)|既定値を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationPoint::GetAnimationVariableList](#getanimationvariablelist)|一覧にカプセル化されたアニメーション変数を追加します。 (上書き[CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist))。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationPoint::operator CPoint](#operator_cpoint)|CAnimationPoint を CPoint に変換します。|  
|[CAnimationPoint::operator =](#operator_eq)|CAnimationPoint ptSrc に割り当てます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationPoint::m_xValue](#m_xvalue)|カプセル化されたアニメーション変数を表す X アニメーション ポイントの座標。|  
|[CAnimationPoint::m_yValue](#m_yvalue)|アニメーション ポイントの Y 座標を表すアニメーションをカプセル化された変数です。|  
  
## <a name="remarks"></a>コメント  
 CAnimationPoint クラスは、CAnimationVariable の&2; つのオブジェクトをカプセル化して、ポイントをアプリケーションで表すことができます。 たとえば、(文字列、円、ポイントなど) など、画面上のオブジェクトの位置をアニメーション化するのにこのクラスを使用できます。 アプリケーションでこのクラスを使用するだけこのクラスのオブジェクトをインスタンス化、CAnimationController::AddAnimationObject を使用してアニメーション コント ローラーを追加および呼び出しに適用される各移行につき AddTransition X および Y 座標。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationPoint`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationPoint::AddTransition  
 X の遷移を追加し、Y 座標。  
  
```  
void AddTransition(
    CBaseTransition* pXTransition,  
    CBaseTransition* pYTransition);
```  
  
### <a name="parameters"></a>パラメーター  
 `pXTransition`  
 X 座標の遷移をへのポインター。  
  
 `pYTransition`  
 Y の移行へのポインターを調整します。  
  
### <a name="remarks"></a>コメント  
 X のアニメーション変数に適用する遷移の内部リストに指定された遷移を追加するには、この関数を呼び出す座標と Y 座標。 切り替え効果を追加すると、いないすぐに適用されるとなり内部リストに格納されています。 遷移 (特定の値のストーリー ボードへの追加) 適用 CAnimationController::AnimateGroup を呼び出すとします。 座標のいずれかの遷移を適用する必要としない場合は、NULL を渡すことができます。  
  
##  <a name="canimationpoint"></a>CAnimationPoint::CAnimationPoint  
 CAnimationPoint オブジェクトを構築します。  
  
```  
CAnimationPoint();

 
CAnimationPoint(
    const CPoint& ptDefault,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptDefault`  
 既定の位置座標を指定します。  
  
 `nGroupID`  
 グループ ID を指定します  
  
 `nObjectID`  
 オブジェクト ID を指定します  
  
 `dwUserData`  
 ユーザー定義データを指定します。  
  
### <a name="remarks"></a>コメント  
 既定のプロパティを持つ CAnimationPoint のオブジェクトを作成します。 ポイント座標を既定値、グループ ID とオブジェクト ID が 0 に設定されます。  
  
##  <a name="getanimationvariablelist"></a>CAnimationPoint::GetAnimationVariableList  
 一覧にカプセル化されたアニメーション変数を追加します。  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>パラメーター  
 `lst`  
 関数から返されたときに、X と Y 座標を表す&2; つの CAnimationVariable オブジェクトへのポインターを格納します。  
  
##  <a name="getdefaultvalue"></a>CAnimationPoint::GetDefaultValue  
 X の既定値を返す座標と Y 座標。  
  
```  
CPoint GetDefaultValue();
```  
  
### <a name="return-value"></a>戻り値  
 既定値を含むポイント。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターまたは SetDefaultValue で以前に設定された既定値を取得するには、この関数を呼び出します。  
  
##  <a name="getvalue"></a>CAnimationPoint::GetValue  
 現在の値を返します。  
  
```  
BOOL GetValue(CPoint& ptValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptValue`  
 出力します。 このメソッドが戻るとき、現在の値が含まれます。  
  
### <a name="return-value"></a>戻り値  
 現在の値の取得が成功した場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 アニメーション ポイントの現在の値を取得するには、この関数を呼び出します。 このメソッドが失敗したか、基になる COM オブジェクトの x、Y 座標が初期化されていない場合は、ptValue には、コンス トラクターまたは SetDefaultValue によって以前に設定された既定値が含まれています。  
  
##  <a name="getx"></a>CAnimationPoint::GetX  
 X 座標の CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetX();
```  
  
### <a name="return-value"></a>戻り値  
 X を表すカプセル化された CAnimationVariable への参照を調整します。  
  
### <a name="remarks"></a>コメント  
 X を表す、基になる CAnimationVariable への直接アクセスを取得するには、このメソッドを呼び出すことができますを調整します。  
  
##  <a name="gety"></a>CAnimationPoint::GetY  
 Y 座標の CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetY();
```  
  
### <a name="return-value"></a>戻り値  
 Y 座標を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>コメント  
 Y 座標を表す、基になる CAnimationVariable への直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="m_xvalue"></a>CAnimationPoint::m_xValue  
 カプセル化されたアニメーション変数を表す X アニメーション ポイントの座標。  
  
```  
CAnimationVariable m_xValue;  
```  
  
##  <a name="m_yvalue"></a>CAnimationPoint::m_yValue  
 アニメーション ポイントの Y 座標を表すアニメーションをカプセル化された変数です。  
  
```  
CAnimationVariable m_yValue;  
```  
  
##  <a name="operator_cpoint"></a>CAnimationPoint::operator CPoint  
 CAnimationPoint を CPoint に変換します。  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>戻り値  
 CPoint として CAnimationPoint の現在の値。  
  
### <a name="remarks"></a>コメント  
 この関数は、GetValue を内部的に呼び出します。 返されるポイントが X の既定値を格納する GetValue 何らかの理由で失敗すると、座標と Y 座標。  
  
##  <a name="operator_eq"></a>CAnimationPoint::operator =  
 CAnimationPoint ptSrc に割り当てます。  
  
```  
void operator=(const CPoint& ptSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptSrc`  
 CPoint またはポイントを表します。  
  
### <a name="remarks"></a>コメント  
 CAnimationPoint ptSrc に割り当てます。 いるアニメーションの開始前にこの演算子は SetDefaultValue を呼び出すため、基になる COM を再作成するオブジェクトの X 座標と Y 座標が作成された場合に行うことをお勧めします。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
##  <a name="setdefaultvalue"></a>CAnimationPoint::SetDefaultValue  
 既定値を設定します。  
  
```  
void SetDefaultValue(const POINT& ptDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptDefault`  
 ポイントの既定値を指定します。  
  
### <a name="remarks"></a>コメント  
 この関数を使用すると、アニメーション オブジェクトを既定値を設定できます。 このメソッドは割り当て、既定値をアニメーション ポイントの座標 X と Y 座標。 作成された場合は、基になる COM オブジェクトも再作成します。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

