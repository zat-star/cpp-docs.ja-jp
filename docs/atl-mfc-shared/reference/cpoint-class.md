---
title: "CPoint クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
dev_langs:
- C++
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
caps.latest.revision: 22
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 6b1afeea5a1d55fb3317b432871f2ed15dd5d19e
ms.lasthandoff: 02/24/2017

---
# <a name="cpoint-class"></a>CPoint クラス
Windows の `POINT` 構造体と同様のものです。  
  
## <a name="syntax"></a>構文  
  
```  
class CPoint : public tagPOINT 
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPoint::CPoint](#cpoint)|`CPoint` を構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPoint::Offset](#offset)|値を追加、 **x**と**y**のメンバー、`CPoint`です。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CPoint::operator-](#operator_-)|差を返す、`CPoint`サイズや、ポイント、または&2; つのポイントまたは負のサイズのオフセットの差をサイズの符号を反転します。|  
|[CPoint::operator! =](#operator_neq)|2 つの地点には、非等値を確認します。|  
|[CPoint::operator +](#operator_add)|合計を返して、`CPoint`サイズやポイント、または`CRect`サイズによって相殺します。|  
|[CPoint::operator + = 演算子](#operator_add_eq)|オフセット`CPoint`サイズまたはポイントを追加しています。|  
|[CPoint::operator =](#operator_-_eq)|オフセット`CPoint`サイズや位置を減算しています。|  
|[CPoint::operator = =](#operator_eq_eq)|2 つのポイント間の等価性を確認します。|  
  
## <a name="remarks"></a>コメント  
 操作するメンバー関数も含まれています。`CPoint`と[ポイント](../../mfc/reference/point-structure1.md)構造体。  
  
 A`CPoint`オブジェクトができる任意の場所を使用、`POINT`構造体を使用します。 [サイズ] と対話するこのクラスの演算子は、両方を受け付ける[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトまたは[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)、構造体の&2; つは交換可能なためです。  
  
> [!NOTE]
>  このクラスから派生、`tagPOINT`構造体。 (名前`tagPOINT`の使用頻度の低い名である、`POINT`構造です)。つまり、このデータ メンバーの`POINT`構造体、`x`と`y`のアクセス可能なデータ メンバーである`CPoint`です。  
  
> [!NOTE]
>  詳細については、ユーティリティ クラスを共有 (のように`CPoint`) を参照してください[共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `tagPOINT`  
  
 `CPoint`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltypes.h  
  
##  <a name="cpoint"></a>CPoint::CPoint
 `CPoint` オブジェクトを構築します。  
  
```  
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `initX`  
 `x` の `CPoint` メンバーの値を指定します。  
  
 `initY`  
 `y` の `CPoint` メンバーの値を指定します。  
  
 `initPt`  
 [ポイント](../../mfc/reference/point-structure1.md)構造または`CPoint`初期化するために使用される値を指定する`CPoint`です。  
  
 `initSize`  
 [サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)初期化するために使用される値を指定する`CPoint`です。  
  
 `dwPoint`  
 `x` の下位ワードに `dwPoint` メンバー、`y` の上位ワードに `dwPoint` メンバーを設定します。  
  
### <a name="remarks"></a>コメント  
 引数を指定しない場合、`x` メンバーおよび `y` メンバーは 0 に設定されます。  
  
### <a name="example"></a>例  
  
```cpp   
CPoint   ptTopLeft(0, 0); 
// works from a POINT, too  
 
POINT   ptHere;  
ptHere.x = 35;  
ptHere.y = 95;  
 
CPoint   ptMFCHere(ptHere);
 
// works from a SIZE 
SIZE   sHowBig;  
sHowBig.cx = 300;  
sHowBig.cy = 10;  
 
CPoint ptMFCBig(sHowBig); 
// or from a DWORD  
 
DWORD   dwSize;  
dwSize = MAKELONG(35, 95);
 
CPoint ptFromDouble(dwSize);
ASSERT(ptFromDouble == ptMFCHere);
```  
  
##  <a name="offset"></a>CPoint::Offset  
 値を追加、 **x**と**y**のメンバー、`CPoint`です。  
  
```  
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *x オフセット*  
 オフセット量の指定、 **x**のメンバー、`CPoint`です。  
  
 *y オフセット*  
 オフセット量の指定、 **y**のメンバー、`CPoint`です。  
  
 `point`  
 量を指定します ([ポイント](../../mfc/reference/point-structure1.md)または`CPoint`) を短縮する、`CPoint`です。  
  
 `size`  
 量を指定します ([サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)または[CSize](../../atl-mfc-shared/reference/csize-class.md)) を短縮する、`CPoint`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&28;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]  
  
##  <a name="operator_eq_eq"></a>CPoint::operator = =  
 2 つのポイント間の等価性を確認します。  
  
```  
BOOL operator==(POINT point) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 含む、[ポイント](../../mfc/reference/point-structure1.md)構造または`CPoint`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 ポイントが等しい場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&29;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]  
  
##  <a name="operator_neq"></a>CPoint::operator! =  
 2 つの地点には、非等値を確認します。  
  
```  
BOOL operator!=(POINT point) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 含む、[ポイント](../../mfc/reference/point-structure1.md)構造または`CPoint`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 ポイントが等しくない場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&30;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]  
  
##  <a name="operator_add_eq"></a>CPoint::operator + = 演算子  
 最初のオーバー ロードを追加するサイズ、`CPoint`です。  
  
```  
void operator+=(SIZE size) throw(); 
void operator+=(POINT point) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 含む、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。  
  
 `point`  
 含む、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 2 番目のオーバー ロードを追加 をポイント、`CPoint`です。  
  
 どちらの場合も、または追加により達成、 **x** (または**cx**) を右辺のオペランドのメンバー、 **x**のメンバー、`CPoint`を追加して、 **y** (または**cy**) を右辺のオペランドのメンバー、 **y**のメンバー、`CPoint`です。  
  
 追加など、`CPoint(5, -7)`を含む変数に`CPoint(30, 40)`に変数が変更される`CPoint(35, 33)`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&31;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]  
  
##  <a name="operator_-_eq"></a>CPoint::operator =  
 最初のオーバー ロードからサイズを減算し、`CPoint`です。  
  
```  
void operator-=(SIZE size) throw(); 
void operator-=(POINT point) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 含む、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。  
  
 `point`  
 含む、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 2 番目のオーバー ロードからポイントを減算し、`CPoint`です。  
  
 差し引いて減算を行うどちらの場合も、 **x** (または**cx**) から右のオペランドのメンバー、 **x**のメンバー、`CPoint`差し引く、 **y** (または**cy**) から右のオペランドのメンバー、 **y**のメンバー、`CPoint`です。  
  
 たとえば、減算`CPoint(5, -7)`を含む変数から`CPoint(30, 40)`に変数が変更される`CPoint(25, 47)`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#32;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]  
  
##  <a name="operator_add"></a>CPoint::operator +  
 この演算子のオフセットを使用して`CPoint`によって、`CPoint`または`CSize`オブジェクト、またはオフセット、`CRect`によって、`CPoint`です。  
  
```  
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 含む、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。  
  
 `point`  
 含む、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトです。  
  
 `lpRect`  
 ポインターを含む、 [RECT](../../mfc/reference/rect-structure1.md)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 A `CPoint` 、サイズをオフセットする、 **CPoint** 、点をオフセットするか、 **CRect**点をオフセットします。  
  
### <a name="remarks"></a>コメント  
 たとえば、最初の 2 つのオーバー ロードのいずれかを使用して、点をオフセット`CPoint(25, -19)`ポイントによって`CPoint(15, 5)`またはサイズ`CSize(15, 5)`値を返します`CPoint(40, -14)`します。  
  
 加算された四角形を返しますポイントに四角形の追加、 **x**と**y**ポイントで指定された値。 たとえば、四角形をオフセットする最後のオーバー ロードを使用して`CRect(125, 219, 325, 419)`ポイントによって`CPoint(25, -19)`返します`CRect(150, 200, 350, 400)`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&33;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]  
  
##  <a name="operator_-"></a>CPoint::operator-  
 減算する最初の&2; つのオーバー ロードのいずれかを使用して、`CPoint`または`CSize`オブジェクトから`CPoint`します。  
  
```  
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 A[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトです。  
  
 `size`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。  
  
 `lpRect`  
 ポインター、 [RECT](../../mfc/reference/rect-structure1.md)構造体、または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 A `CSize`&2; 点間の違いは、 `CPoint` 、サイズの否定をオフセットする、 `CRect` 、ポイントの否定をオフセットする、または`CPoint`は、ポイントの符号を反転します。  
  
### <a name="remarks"></a>コメント  
 3 番目のオーバー ロードのオフセット、`CRect`の拒否によって`CPoint`します。 最後に、単項演算子を使用して、符号を反転`CPoint`します。  
  
 たとえば、最初のオーバー ロードを使用して、2 つのポイントの差を求める`CPoint(25, -19)`と`CPoint(15, 5)`返します`CSize(10, -24)`します。  
  
 減算、`CSize`から`CPoint`は上記と同じ計算が、返す、`CPoint`オブジェクトは、`CSize`オブジェクトです。 たとえば、2 番目のオーバー ロードを使用して、ポイントの差を求める`CPoint(25, -19)`とサイズ`CSize(15, 5)`を返します`CPoint(10, -24)`します。  
  
 符号を反転して四角形のオフセットを返す四角形の点から減算すること、 **x**と**y**ポイントで指定された値。 たとえば、四角形をオフセットする最後のオーバー ロードを使用して`CRect(125, 200, 325, 400)`ポイントによって`CPoint(25, -19)`返します`CRect(100, 219, 300, 419)`します。  
  
 点の符号を反転するのにには、単項演算子を使用します。 たとえば、ポイントと単項演算子を使用して`CPoint(25, -19)`返します`CPoint(-25, 19)`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&34;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [POINT 構造体](../../mfc/reference/point-structure1.md)   
 [CRect クラス](../../atl-mfc-shared/reference/crect-class.md)   
 [CSize クラス](../../atl-mfc-shared/reference/csize-class.md)




