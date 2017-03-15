---
title: "CD2DGeometrySink クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DGeometrySink
- CD2DGeometrySink
dev_langs:
- C++
helpviewer_keywords:
- CD2DGeometrySink class
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
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
ms.openlocfilehash: 8a51d9475437ae460340d419a88bc46effa81f5f
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dgeometrysink-class"></a>CD2DGeometrySink クラス
ID2D1GeometrySink のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DGeometrySink;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometrySink::CD2DGeometrySink](#cd2dgeometrysink)|CD2DPathGeometry オブジェクトから CD2DGeometrySink オブジェクトを構築します。|  
|[CD2DGeometrySink:: ~ CD2DGeometrySink](#_dtorcd2dgeometrysink)|デストラクターです。 D2D geometry シンク オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometrySink::AddArc](#addarc)|1 つの円弧をパス ジオメトリに追加します。|  
|[CD2DGeometrySink::AddBezier](#addbezier)|現在のポイントと指定したエンドポイント間で&3; 次ベジエ曲線を作成します。|  
|[CD2DGeometrySink::AddBeziers](#addbeziers)|3 次ベジエ曲線のシーケンスを作成し、ジオメトリ シンクに追加します。|  
|[CD2DGeometrySink::AddLine](#addline)|現在のポイントと指定したエンドポイント間の直線セグメントを作成し、ジオメトリのシンクに追加します。|  
|[CD2DGeometrySink::AddLines](#addlines)|指定されたポイントを使用して線のシーケンスを作成し、ジオメトリのシンクにします。|  
|[CD2DGeometrySink::AddQuadraticBezier](#addquadraticbezier)|現在のポイントと指定したエンドポイント間で&2; 次ベジエ曲線を作成します。|  
|[CD2DGeometrySink::AddQuadraticBeziers](#addquadraticbeziers)|配列で&1; 回の呼び出しには、2 次ベジエ セグメントのシーケンスを追加します。|  
|[CD2DGeometrySink::BeginFigure](#beginfigure)|指定したポイントに新しい図形を開始します。|  
|[CD2DGeometrySink::Close](#close)|ジオメトリのシンクを閉じる|  
|[CD2DGeometrySink::EndFigure](#endfigure)|現在の図を終了します。必要に応じて、ウィンドウが閉じます。|  
|[CD2DGeometrySink::Get](#get)|返します。 ID2D1GeometrySink インターフェイス|  
|[CD2DGeometrySink::IsValid](#isvalid)|ジオメトリ シンクの有効性を確認します。|  
|[CD2DGeometrySink::SetFillMode](#setfillmode)|この geometry シンクによって記述された geometry 内のポイントは、外にある点を判断するために使用するメソッドを指定します。|  
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|ジオメトリのシンクに追加された新しいセグメントに適用する線と結合のオプションを指定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometrySink::operator ID2D1GeometrySink *](#operator_id2d1geometrysink_star)|返します。 ID2D1GeometrySink インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometrySink::m_pSink](#m_psink)|ID2D1GeometrySink へのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CD2DGeometrySink`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dgeometrysinka--cd2dgeometrysinkcd2dgeometrysink"></a><a name="_dtorcd2dgeometrysink"></a>CD2DGeometrySink:: ~ CD2DGeometrySink  
 デストラクターです。 D2D geometry シンク オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DGeometrySink();
```  
  
##  <a name="a-nameaddarca--cd2dgeometrysinkaddarc"></a><a name="addarc"></a>CD2DGeometrySink::AddArc  
 1 つの円弧をパス ジオメトリに追加します。  
  
```  
void AddArc(const D2D1_ARC_SEGMENT& arc);
```  
  
### <a name="parameters"></a>パラメーター  
 `arc`  
 円弧のセグメントの図に追加するには  
  
##  <a name="a-nameaddbeziera--cd2dgeometrysinkaddbezier"></a><a name="addbezier"></a>CD2DGeometrySink::AddBezier  
 現在のポイントと指定したエンドポイント間で&3; 次ベジエ曲線を作成します。  
  
```  
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>パラメーター  
 `bezier`  
 制御点と追加をベジエ曲線の終点を記述する構造体。  
  
##  <a name="a-nameaddbeziersa--cd2dgeometrysinkaddbeziers"></a><a name="addbeziers"></a>CD2DGeometrySink::AddBeziers  
 3 次ベジエ曲線のシーケンスを作成し、ジオメトリ シンクに追加します。  
  
```  
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,  
    D2D1_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>パラメーター  
 `beziers`  
 作成するベジエ曲線を表すベジエ セグメントの配列。 配列の最初のベジエ セグメントの終了点のジオメトリ シンクの現在のポイント (描画された最後のセグメントまたは BeginFigure で指定された位置の終了位置) から、曲線が描画されます。 配列に追加のベジエ セグメントが含まれている場合、後続の各ベジエ セグメントは開始ポイントとして前のベジエ セグメントの終了位置を使用します。  
  
##  <a name="a-nameaddlinea--cd2dgeometrysinkaddline"></a><a name="addline"></a>CD2DGeometrySink::AddLine  
 現在のポイントと指定したエンドポイント間の直線セグメントを作成し、ジオメトリのシンクに追加します。  
  
```  
void AddLine(CD2DPointF point);
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 描画する線の終点です。  
  
##  <a name="a-nameaddlinesa--cd2dgeometrysinkaddlines"></a><a name="addlines"></a>CD2DGeometrySink::AddLines  
 指定されたポイントを使用して線のシーケンスを作成し、ジオメトリのシンクにします。  
  
```  
void AddLines(
    const CArray<CD2DPointF,  
    CD2DPointF>& points);
```  
  
### <a name="parameters"></a>パラメーター  
 `points`  
 描画する行を&1; つまたは複数の点の配列。 配列内の最初の点のジオメトリ シンクの現在のポイント (描画された最後のセグメントまたは BeginFigure で指定された位置の終了位置) から線が描画されます。 配列に追加の点が含まれている場合、行は最初の点から&3; 番目のポイントには、2 番目の点から、配列の&2; つ目のポイントでは描画されます。 描画する線の終点の一連の配列。  
  
##  <a name="a-nameaddquadraticbeziera--cd2dgeometrysinkaddquadraticbezier"></a><a name="addquadraticbezier"></a>CD2DGeometrySink::AddQuadraticBezier  
 現在のポイントと指定したエンドポイント間で&2; 次ベジエ曲線を作成します。  
  
```  
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>パラメーター  
 `bezier`  
 管理ポイントとを追加する二次ベジエ曲線の終了位置を記述する構造体。  
  
##  <a name="a-nameaddquadraticbeziersa--cd2dgeometrysinkaddquadraticbeziers"></a><a name="addquadraticbeziers"></a>CD2DGeometrySink::AddQuadraticBeziers  
 配列で&1; 回の呼び出しには、2 次ベジエ セグメントのシーケンスを追加します。  
  
```  
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,  
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>パラメーター  
 `beziers`  
 2 次ベジエ セグメントの一連の配列。  
  
##  <a name="a-namebeginfigurea--cd2dgeometrysinkbeginfigure"></a><a name="beginfigure"></a>CD2DGeometrySink::BeginFigure  
 指定したポイントに新しい図形を開始します。  
  
```  
void BeginFigure(
    CD2DPointF startPoint,  
    D2D1_FIGURE_BEGIN figureBegin);
```  
  
### <a name="parameters"></a>パラメーター  
 `startPoint`  
 新しい図を開始位置を示すポイント。  
  
 `figureBegin`  
 かどうか新しい図では、穴の空いたまたは塗りつぶしをする必要があります。  
  
##  <a name="a-namecd2dgeometrysinka--cd2dgeometrysinkcd2dgeometrysink"></a><a name="cd2dgeometrysink"></a>CD2DGeometrySink::CD2DGeometrySink  
 CD2DPathGeometry オブジェクトから CD2DGeometrySink オブジェクトを構築します。  
  
```  
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```  
  
### <a name="parameters"></a>パラメーター  
 `pathGeometry`  
 既存の CD2DPathGeometry オブジェクトです。  
  
##  <a name="a-nameclosea--cd2dgeometrysinkclose"></a><a name="close"></a>CD2DGeometrySink::Close  
 ジオメトリのシンクを閉じる  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外。それ以外の場合は FALSE。  
  
##  <a name="a-nameendfigurea--cd2dgeometrysinkendfigure"></a><a name="endfigure"></a>CD2DGeometrySink::EndFigure  
 現在の図を終了します。必要に応じて、ウィンドウが閉じます。  
  
```  
void EndFigure(D2D1_FIGURE_END figureEnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `figureEnd`  
 現在の図を閉じるかどうかを示す値です。 図を終了している場合、現在のポイントと BeginFigure で指定された開始点の間で線を描画します。  
  
##  <a name="a-namegeta--cd2dgeometrysinkget"></a><a name="get"></a>CD2DGeometrySink::Get  
 返します。 ID2D1GeometrySink インターフェイス  
  
```  
ID2D1GeometrySink* Get();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1GeometrySink インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="a-nameisvalida--cd2dgeometrysinkisvalid"></a><a name="isvalid"></a>CD2DGeometrySink::IsValid  
 ジオメトリ シンクの有効性を確認します。  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ジオメトリのシンクが有効である場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="a-namempsinka--cd2dgeometrysinkmpsink"></a><a name="m_psink"></a>CD2DGeometrySink::m_pSink  
 ID2D1GeometrySink へのポインター。  
  
```  
ID2D1GeometrySink* m_pSink;  
```  
  
##  <a name="a-nameoperatorid2d1geometrysinkstara--cd2dgeometrysinkoperator-id2d1geometrysink"></a><a name="operator_id2d1geometrysink_star"></a>CD2DGeometrySink::operator ID2D1GeometrySink *  
 返します。 ID2D1GeometrySink インターフェイス  
  
```  
operator ID2D1GeometrySink*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1GeometrySink インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="a-namesetfillmodea--cd2dgeometrysinksetfillmode"></a><a name="setfillmode"></a>CD2DGeometrySink::SetFillMode  
 この geometry シンクによって記述された geometry 内のポイントは、外にある点を判断するために使用するメソッドを指定します。  
  
```  
void SetFillMode(D2D1_FILL_MODE fillMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `fillMode`  
 メソッドが、指定された点がジオメトリの一部であるかどうかを確認するために使用します。  
  
##  <a name="a-namesetsegmentflagsa--cd2dgeometrysinksetsegmentflags"></a><a name="setsegmentflags"></a>CD2DGeometrySink::SetSegmentFlags  
 ジオメトリのシンクに追加された新しいセグメントに適用する線と結合のオプションを指定します。  
  
```  
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `vertexFlags`  
 ジオメトリのシンクに追加された新しいセグメントに適用する線と結合のオプションです。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

