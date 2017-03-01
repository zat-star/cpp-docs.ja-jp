---
title: "CD2DGeometry クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DGeometry
- afxrendertarget/CD2DGeometry
dev_langs:
- C++
helpviewer_keywords:
- CD2DGeometry class
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
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
ms.openlocfilehash: 948b2e2154259557e3a52c2045586cffce2a16f8
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dgeometry-class"></a>CD2DGeometry クラス
ID2D1Geometry のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DGeometry : public CD2DResource;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometry::CD2DGeometry](#cd2dgeometry)|CD2DGeometry のオブジェクトを構築します。|  
|[CD2DGeometry:: ~ CD2DGeometry](#_dtorcd2dgeometry)|デストラクターです。 D2D geometry オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometry::Attach](#attach)|オブジェクトにリソース インタ フェースを既存の接続|  
|[CD2DGeometry::CombineWithGeometry](#combinewithgeometry)|指定したジオメトリをこの geometry を結合し、その結果、ID2D1SimplifiedGeometrySink に格納します。|  
|[CD2DGeometry::CompareWithGeometry](#comparewithgeometry)|このジオメトリと指定された geometry の交差部分をについて説明します。 フラット化の指定された許容範囲を使用して比較を実行します。|  
|[CD2DGeometry::ComputeArea](#computearea)|ジオメトリの領域が計算された後に指定した行列を使用して変換し、指定された許容範囲を使用してフラット化します。|  
|[CD2DGeometry::ComputeLength](#computelength)|各セグメントは直線にロールバックされたかのように、ジオメトリの長さを計算します。|  
|[CD2DGeometry::ComputePointAtLength](#computepointatlength)|ジオメトリに沿って指定された距離にあるポイントおよびタンジェント ベクトルが計算された後に指定した行列を使用して変換し、指定された許容範囲を使用してフラット化します。|  
|[CD2DGeometry::Destroy](#destroy)|CD2DGeometry オブジェクトを破棄します。 (上書き[CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy))。|  
|[CD2DGeometry::Detach](#detach)|オブジェクトからリソース インタ フェースをデタッチします。|  
|[CD2DGeometry::FillContainsPoint](#fillcontainspoint)|ジオメトリで埋められた領域はフラット化の指定された許容範囲を指定する指定された時点を含めるかどうかを示します。|  
|[CD2DGeometry::Get](#get)|返します。 ID2D1Geometry インターフェイス|  
|[CD2DGeometry::GetBounds](#getbounds)||  
|[CD2DGeometry::GetWidenedBounds](#getwidenedbounds)|指定した線の幅とスタイルによって上位変換して指定した行列によって変換された後は、ジオメトリの境界を取得します。|  
|[CD2DGeometry::IsValid](#isvalid)|リソースの有効性をチェックする (上書き[CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid))。|  
|[CD2DGeometry::Outline](#outline)|Geometry の輪郭を計算し、その結果を ID2D1SimplifiedGeometrySink に書き込みます。|  
|[CD2DGeometry::Simplify](#simplify)|線および (必要に応じて)&3; 次ベジエ曲線のみを含み、結果を ID2D1SimplifiedGeometrySink に書き込むジオメトリの簡略版を作成します。|  
|[CD2DGeometry::StrokeContainsPoint](#strokecontainspoint)|ジオメトリのストロークに指定したストロークの太さ、スタイル、および変換を指定する指定された時点が含まれているかどうかを判断します。|  
|[CD2DGeometry::Tessellate](#tessellate)|指定した行列を使用して変換された後に、geometry をカバーし、指定された許容範囲を使用してフラット化する時計回りの三角形のセットを作成します。|  
|[CD2DGeometry::Widen](#widen)|ジオメトリは拡大し、指定したストロークと、ID2D1SimplifiedGeometrySink を結果に出力しています。 指定した行列を使用して変換し、指定された許容範囲を使用してフラット化します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometry::operator ID2D1Geometry *](#operator_id2d1geometry_star)|返します。 ID2D1Geometry インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometry::m_pGeometry](#m_pgeometry)|ID2D1Geometry へのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DGeometry`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dgeometrya--cd2dgeometrycd2dgeometry"></a><a name="_dtorcd2dgeometry"></a>CD2DGeometry:: ~ CD2DGeometry  
 デストラクターです。 D2D geometry オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DGeometry();
```  
  
##  <a name="a-nameattacha--cd2dgeometryattach"></a><a name="attach"></a>CD2DGeometry::Attach  
 オブジェクトにリソース インタ フェースを既存の接続  
  
```  
void Attach(ID2D1Geometry* pResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `pResource`  
 既存のリソースのインターフェイスです。 NULL にすることはできません。  
  
##  <a name="a-namecd2dgeometrya--cd2dgeometrycd2dgeometry"></a><a name="cd2dgeometry"></a>CD2DGeometry::CD2DGeometry  
 CD2DGeometry のオブジェクトを構築します。  
  
```  
CD2DGeometry(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentTarget`  
 レンダー ターゲットへのポインター。  
  
 `bAutoDestroy`  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
##  <a name="a-namecombinewithgeometrya--cd2dgeometrycombinewithgeometry"></a><a name="combinewithgeometry"></a>CD2DGeometry::CombineWithGeometry  
 指定したジオメトリをこの geometry を結合し、その結果、ID2D1SimplifiedGeometrySink に格納します。  
  
```  
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,  
    D2D1_COMBINE_MODE combineMode,  
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `inputGeometry`  
 このインスタンスと結合するジオメトリ。  
  
 `combineMode`  
 結合操作を実行する型。  
  
 `inputGeometryTransform`  
 結合する前に inputGeometry に適用する変換です。  
  
 `geometrySink`  
 結合操作の結果。  
  
 `flatteningTolerance`  
 ジオメトリの多角形近似の点の間の距離の上限。 小さい値はより正確な結果を生成しますが、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="a-namecomparewithgeometrya--cd2dgeometrycomparewithgeometry"></a><a name="comparewithgeometry"></a>CD2DGeometry::CompareWithGeometry  
 このジオメトリと指定された geometry の交差部分をについて説明します。 フラット化の指定された許容範囲を使用して比較を実行します。  
  
```  
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,  
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `inputGeometry`  
 テストするジオメトリ。  
  
 `inputGeometryTransform`  
 InputGeometry に適用する変換です。  
  
 `flatteningTolerance`  
 ジオメトリの多角形近似の点の間の距離の上限。 小さい値はより正確な結果を生成しますが、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="a-namecomputeareaa--cd2dgeometrycomputearea"></a><a name="computearea"></a>CD2DGeometry::ComputeArea  
 ジオメトリの領域が計算された後に指定した行列を使用して変換し、指定された許容範囲を使用してフラット化します。  
  
```  
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    FLOAT& area,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `worldTransform`  
 その領域を計算する前にこのジオメトリに適用する変換です。  
  
 `area`  
 このメソッドが戻るとき、変換されたフラット化されたバージョンのこの geometry の領域へのポインターが含まれています。 このパラメーターには、記憶域を割り当てる必要があります。  
  
 `flatteningTolerance`  
 ジオメトリの多角形近似の点の間の距離の上限。 小さい値はより正確な結果を生成しますが、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="a-namecomputelengtha--cd2dgeometrycomputelength"></a><a name="computelength"></a>CD2DGeometry::ComputeLength  
 各セグメントは直線にロールバックされたかのように、ジオメトリの長さを計算します。  
  
```  
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    FLOAT& length,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `worldTransform`  
 その長さを計算する前に、ジオメトリに適用する変換です。  
  
 `length`  
 このメソッドが戻るときに、ジオメトリの長さへのポインターが含まれています。 終了した場合は、長さには、暗黙的な終了セグメントが含まれています。 このパラメーターには、記憶域を割り当てる必要があります。  
  
 `flatteningTolerance`  
 ジオメトリの多角形近似の点の間の距離の上限。 小さい値はより正確な結果を生成しますが、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="a-namecomputepointatlengtha--cd2dgeometrycomputepointatlength"></a><a name="computepointatlength"></a>CD2DGeometry::ComputePointAtLength  
 ジオメトリに沿って指定された距離にあるポイントおよびタンジェント ベクトルが計算された後に指定した行列を使用して変換し、指定された許容範囲を使用してフラット化します。  
  
```  
BOOL ComputePointAtLength(
    FLOAT length,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    CD2DPointF& point,  
    CD2DPointF& unitTangentVector,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `length`  
 ポイントと検索に接するのジオメトリに沿った距離。 この距離が少なく、0 の場合は、このメソッドは、ジオメトリの 1 つ目のポイントを計算します。 この距離は、ジオメトリのサイズより大きい値は、このメソッドは、ジオメトリの最後の点を計算します。  
  
 `worldTransform`  
 指定したポイントおよびタンジェントを計算する前に、ジオメトリに適用する変換です。  
  
 `point`  
 指定された距離のジオメトリに沿った位置。 このポイントが、x と y として NaN を含む、ジオメトリが空の場合の値。  
  
 `unitTangentVector`  
 このメソッドが戻るときに、指定されたジオメトリに沿った距離にある正接ベクトルへのポインターが含まれています。 このベクトルとその x および y NaN を含む、ジオメトリが空の場合の値。 このパラメーターには、記憶域を割り当てる必要があります。  
  
 `flatteningTolerance`  
 ジオメトリの多角形近似の点の間の距離の上限。 小さい値はより正確な結果を生成しますが、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="a-namedestroya--cd2dgeometrydestroy"></a><a name="destroy"></a>CD2DGeometry::Destroy  
 CD2DGeometry オブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dgeometrydetach"></a><a name="detach"></a>CD2DGeometry::Detach  
 オブジェクトからリソース インタ フェースをデタッチします。  
  
```  
ID2D1Geometry* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたリソース インタ フェースへのポインター。  
  
##  <a name="a-namefillcontainspointa--cd2dgeometryfillcontainspoint"></a><a name="fillcontainspoint"></a>CD2DGeometry::FillContainsPoint  
 ジオメトリで埋められた領域はフラット化の指定された許容範囲を指定する指定された時点を含めるかどうかを示します。  
  
```  
BOOL FillContainsPoint(
    CD2DPointF point,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    BOOL* contains,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 テストする点です。  
  
 `worldTransform`  
 含有をテストする前にジオメトリに適用する変換です。  
  
 `contains`  
 このメソッドが戻るとき、ジオメトリを塗りつぶし領域には、ポイントが含まれている場合は TRUE であるブール値が含まれています。それ以外の場合は FALSE。 このパラメーターには、記憶域を割り当てる必要があります。  
  
 `flatteningTolerance`  
 これを使用した数値の精度正確なジオメトリック パスとパスの交差部分を計算します。 許容値より小さいから塗りつぶしを未適用ポイントは内部考慮されます。 小さい値はより正確な結果を生成しますが、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="a-namegeta--cd2dgeometryget"></a><a name="get"></a>CD2DGeometry::Get  
 返します。 ID2D1Geometry インターフェイス  
  
```  
ID2D1Geometry* Get();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1Geometry インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="a-namegetboundsa--cd2dgeometrygetbounds"></a><a name="getbounds"></a>CD2DGeometry::GetBounds  
  
```   
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,  
CD2DRectF& bounds) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `worldTransform`  
 `bounds`  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-namegetwidenedboundsa--cd2dgeometrygetwidenedbounds"></a><a name="getwidenedbounds"></a>CD2DGeometry::GetWidenedBounds  
 指定した線の幅とスタイルによって上位変換して指定した行列によって変換された後は、ジオメトリの境界を取得します。  
  
```  
BOOL GetWidenedBounds(
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    CD2DRectF& bounds,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `strokeWidth`  
 外枠を描画してジオメトリを拡大する量。  
  
 `strokeStyle`  
 ジオメトリは拡大し、線のスタイル。  
  
 `worldTransform`  
 ジオメトリの変換後、およびジオメトリが描画した後、ジオメトリに適用する変換です。  
  
 `bounds`  
 このメソッドが戻るとき、拡張された geometry の境界を格納します。 このパラメーターには、記憶域を割り当てる必要があります。  
  
 `flatteningTolerance`  
 ジオメトリの多角形近似の点の間の距離の上限。 小さい値はより正確な結果を生成しますが、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="a-nameisvalida--cd2dgeometryisvalid"></a><a name="isvalid"></a>CD2DGeometry::IsValid  
 リソースの有効性のチェック  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リソースが無効である場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="a-namempgeometrya--cd2dgeometrympgeometry"></a><a name="m_pgeometry"></a>CD2DGeometry::m_pGeometry  
 ID2D1Geometry へのポインター。  
  
```  
ID2D1Geometry* m_pGeometry;  
```  
  
##  <a name="a-nameoperatorid2d1geometrystara--cd2dgeometryoperator-id2d1geometry"></a><a name="operator_id2d1geometry_star"></a>CD2DGeometry::operator ID2D1Geometry *  
 返します。 ID2D1Geometry インターフェイス  
  
```  
operator ID2D1Geometry*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1Geometry インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="a-nameoutlinea--cd2dgeometryoutline"></a><a name="outline"></a>CD2DGeometry::Outline  
 Geometry の輪郭を計算し、その結果を ID2D1SimplifiedGeometrySink に書き込みます。  
  
```  
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `worldTransform`  
 ジオメトリのアウトラインに適用する変換です。  
  
 `geometrySink`  
 ジオメトリがアウトラインを変換 ID2D1SimplifiedGeometrySink が追加されます。  
  
 `flatteningTolerance`  
 ジオメトリの多角形近似の点の間の距離の上限。 小さい値はより正確な結果を生成しますが、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="a-namesimplifya--cd2dgeometrysimplify"></a><a name="simplify"></a>CD2DGeometry::Simplify  
 線および (必要に応じて)&3; 次ベジエ曲線のみを含み、結果を ID2D1SimplifiedGeometrySink に書き込むジオメトリの簡略版を作成します。  
  
```  
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `simplificationOption`  
 簡略化されたジオメトリのカーブを含めるかどうかを指定する値。  
  
 `worldTransform`  
 簡略化されたジオメトリに適用する変換です。  
  
 `geometrySink`  
 ID2D1SimplifiedGeometrySink が簡略化されたジオメトリが追加されます。  
  
 `flatteningTolerance`  
 ジオメトリの多角形近似の点の間の距離の上限。 小さい値はより正確な結果を生成しますが、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="a-namestrokecontainspointa--cd2dgeometrystrokecontainspoint"></a><a name="strokecontainspoint"></a>CD2DGeometry::StrokeContainsPoint  
 ジオメトリのストロークに指定したストロークの太さ、スタイル、および変換を指定する指定された時点が含まれているかどうかを判断します。  
  
```  
BOOL StrokeContainsPoint(
    CD2DPointF point,  
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    BOOL* contains,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 含有をテストする点です。  
  
 `strokeWidth`  
 適用する線の太さ。  
  
 `strokeStyle`  
 適用する線のスタイル。  
  
 `worldTransform`  
 線のジオメトリに適用する変換です。  
  
 `contains`  
 このメソッドが戻るとき、ジオメトリの線には、指定した点が含まれている場合に TRUE に設定するブール値が含まれています。それ以外の場合は FALSE。 このパラメーターには、記憶域を割り当てる必要があります。  
  
 `flatteningTolerance`  
 これを使用した数値の精度正確なジオメトリック パスとパスの交差部分を計算します。 許容値より小さいからストロークを未適用ポイントは内部考慮されます。 小さい値はより正確な結果を生成しますが、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="a-nametessellatea--cd2dgeometrytessellate"></a><a name="tessellate"></a>CD2DGeometry::Tessellate  
 指定した行列を使用して変換された後に、geometry をカバーし、指定された許容範囲を使用してフラット化する時計回りの三角形のセットを作成します。  
  
```  
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1TessellationSink* tessellationSink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `worldTransform`  
 この geometry、または NULL に適用する変換です。  
  
 `tessellationSink`  
 ID2D1TessellationSink が先、テセレーションされたが追加されます。  
  
 `flatteningTolerance`  
 ジオメトリの多角形近似の点の間の距離の上限。 小さい値はより正確な結果を生成しますが、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="a-namewidena--cd2dgeometrywiden"></a><a name="widen"></a>CD2DGeometry::Widen  
 ジオメトリは拡大し、指定したストロークと、ID2D1SimplifiedGeometrySink を結果に出力しています。 指定した行列を使用して変換し、指定された許容範囲を使用してフラット化します。  
  
```  
BOOL Widen(
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `strokeWidth`  
 ジオメトリの幅を広げます量。  
  
 `strokeStyle`  
 Geometry、または NULL に適用する線のスタイル。  
  
 `worldTransform`  
 それを拡大した後、ジオメトリに適用する変換です。  
  
 `geometrySink`  
 ID2D1SimplifiedGeometrySink が拡張されたジオメトリが追加されます。  
  
 `flatteningTolerance`  
 ジオメトリの多角形近似の点の間の距離の上限。 小さい値はより正確な結果を生成しますが、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

