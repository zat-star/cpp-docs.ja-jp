---
title: "CComSafeArray クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSafeArray
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e78c0cb7a0e2fb6cc1e1ac4bba9186d4beee98b4
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsafearray-class"></a>CComSafeArray クラス
このクラスは、 **SAFEARRAY** 構造体のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 配列に格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComSafeArray::CComSafeArray](#ccomsafearray)|コンストラクターです。|  
|[CComSafeArray:: ~ CComSafeArray](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComSafeArray::Add](#add)|1 つ以上の要素または&1; つの **SAFEARRAY** 構造体を `CComSafeArray`に追加します。|  
|[CComSafeArray::Attach](#attach)|**SAFEARRAY** 構造体を `CComSafeArray` オブジェクトにアタッチします。|  
|[CComSafeArray::CopyFrom](#copyfrom)|**SAFEARRAY** 構造体の内容を `CComSafeArray` オブジェクトにコピーします。|  
|[CComSafeArray::CopyTo](#copyto)|`CComSafeArray` オブジェクトのコピーを作成します。|  
|[CComSafeArray::Create](#create)|
          `CComSafeArray` オブジェクトを作成します。|  
|[CComSafeArray::Destroy](#destroy)|`CComSafeArray` オブジェクトを破棄します。|  
|[CComSafeArray::Detach](#detach)|**オブジェクトから** SAFEARRAY `CComSafeArray` をデタッチします。|  
|[CComSafeArray::GetAt](#getat)|1 次元配列から&1; つの要素を取得します。|  
|[CComSafeArray::GetCount](#getcount)|配列内の要素の数を返します。|  
|[CComSafeArray::GetDimensions](#getdimensions)|配列内の次元数を返します。|  
|[CComSafeArray::GetLowerBound](#getlowerbound)|配列の指定した次元の下限を返します。|  
|[CComSafeArray::GetSafeArrayPtr](#getsafearrayptr)|`m_psa` データ メンバーのアドレスを返します。|  
|[CComSafeArray::GetType](#gettype)|配列に格納されているデータの型を返します。|  
|[CComSafeArray::GetUpperBound](#getupperbound)|配列の任意の次元の上限を返します。|  
|[CComSafeArray::IsSizable](#issizable)|`CComSafeArray` オブジェクトのサイズを変更できるかどうかをテストします。|  
|[CComSafeArray::MultiDimGetAt](#multidimgetat)|多次元配列から&1; つの要素を取得します。|  
|[CComSafeArray::MultiDimSetAt](#multidimsetat)|多次元配列の要素の値を設定します。|  
|[CComSafeArray::Resize](#resize)|`CComSafeArray` オブジェクトのサイズを変更します。|  
|[CComSafeArray::SetAt](#setat)|1 次元配列の要素の値を設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CComSafeArray::operator LPSAFEARRAY](#operator_lpsafearray)|値を **SAFEARRAY** ポインターにキャストします。|  
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|配列から要素を取得します。|  
|[CComSafeArray::operator =](#operator_eq)|代入演算子。|  

  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComSafeArray::m_psa](#m_psa)|このデータ メンバーは、 **SAFEARRAY** 構造体のアドレスを保持します。|  
  
## <a name="remarks"></a>コメント  
 `CComSafeArray`ラッパーを提供、 [SAFEARRAY 型](http://msdn.microsoft.com/en-us/9ec8025b-4763-4526-ab45-390c5d8b3b1e)クラスを作成および管理のほとんどすべてのバリエーションでサポートされている型の単一と多次元の配列を簡単になります。  
  
 `CComSafeArray` によりプロセス間での配列の受け渡しが単純化され、配列インデックスの値を上限と下限に照合することでセキュリティがさらに向上します。  
  
 `CComSafeArray` の下限は任意のユーザー定義値で開始できますが、C++ を通じてアクセスされる配列の下限は 0 にする必要があります。 Visual Basic などの他の言語では、別の境界値 (たとえば、-10 ～ 10) を使用できます。  
  
 使用[CComSafeArray::Create](#create)を作成する、`CComSafeArray`オブジェクト、および[CComSafeArray::Destroy](#destroy)を削除します。  
  
 `CComSafeArray` には、VARIANT データ型の次のサブセットを格納できます。  
  
|VARTYPE|説明|  
|-------------|-----------------|  
|VT_I1|char|  
|VT_I2|short|  
|VT_I4|int|  
|VT_I4|long|  
|VT_I8|longlong|  
|VT_UI1|byte|  
|VT_UI2|ushort|  
|VT_UI4|uint|  
|VT_UI4|ulong|  
|VT_UI8|ulonglong|  
|VT_R4|float|  
|VT_R8|double|  
|VT_DECIMAL|10 進ポインター|  
|VT_VARIANT|バリアント ポインター|  
|VT_CY|Currency データ型|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsafe.h  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&75;](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]  
  
##  <a name="a-nameadda--ccomsafearrayadd"></a><a name="add"></a>CComSafeArray::Add  
 1 つ以上の要素または&1; つの **SAFEARRAY** 構造体を `CComSafeArray`に追加します。  
  
```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `psaSrc`  
 ポインター、 **SAFEARRAY**オブジェクトです。  
  
 `ulCount`  
 配列に追加するオブジェクトの数。  
  
 *pT*  
 配列に追加する&1; つまたは複数のオブジェクトへのポインター。  
  
 *t*  
 配列に追加するオブジェクトへの参照。  
  
 `bCopy`  
 データのコピーを作成するかどうかを示します。 既定値は**TRUE**します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 新しいオブジェクトは、既存の末尾に追加されます。 **SAFEARRAY**オブジェクトです。 多次元オブジェクトを追加する**SAFEARRAY**オブジェクトがサポートされていません。 既存のオブジェクトの配列を追加するときに、両方の配列は同じ型の要素を含める必要があります。  
  
 `bCopy`にフラグが考慮されるときに型の要素`BSTR`または**VARIANT**配列に追加されます。 既定値の**TRUE**により、配列に要素が追加されたときに、データの新しいコピーを作成します。  
  
##  <a name="a-nameattacha--ccomsafearrayattach"></a><a name="attach"></a>CComSafeArray::Attach  
 **SAFEARRAY** 構造体を `CComSafeArray` オブジェクトにアタッチします。  
  
```
HRESULT Attach(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `psaSrc`  
 ポインター、 **SAFEARRAY**構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 アタッチ、 **SAFEARRAY**構造の`CComSafeArray`オブジェクト、既存の`CComSafeArray`使用可能なメソッドです。  
  
##  <a name="a-nameccomsafearraya--ccomsafearrayccomsafearray"></a><a name="ccomsafearray"></a>CComSafeArray::CComSafeArray  
 コンストラクターです。  
  
```
CComSafeArray();
CComSafeArray(const SAFEARRAYBOUND& bound);
CComSafeArray(ULONG  ulCount, LONG lLBound = 0);
CComSafeArray(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
CComSafeArray(const CComSafeArray& saSrc);
CComSafeArray(const SAFEARRAY& saSrc);
CComSafeArray(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `bound`  
 A **SAFEARRAYBOUND**構造体。  
  
 `ulCount`  
 配列の要素数。  
  
 `lLBound`  
 下限値。つまり、配列の最初の要素のインデックス。  
  
 `pBound`  
 ポインター、 **SAFEARRAYBOUND**構造体。  
  
 `uDims`  
 配列の次元の数。  
  
 `saSrc`  
 参照、 **SAFEARRAY**構造または`CComSafeArray`オブジェクトです。 いずれの場合は、コンス トラクターは、作成した後、配列は参照しないように、配列のコピーを作成するこの参照を使用します。  
  
 `psaSrc`  
 ポインター、 **SAFEARRAY**構造体。 コンス トラクターでは、このアドレスを使用して、作成した後、配列は参照しないように、配列のコピーを作成します。  
  
### <a name="remarks"></a>コメント  
 
          `CComSafeArray` オブジェクトを作成します。  
  
##  <a name="a-namedtora--ccomsafearrayccomsafearray"></a><a name="dtor"></a>CComSafeArray:: ~ CComSafeArray  
 デストラクターです。  
  
```
~CComSafeArray() throw()
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="a-namecopyfroma--ccomsafearraycopyfrom"></a><a name="copyfrom"></a>CComSafeArray::CopyFrom  
 **SAFEARRAY** 構造体の内容を `CComSafeArray` オブジェクトにコピーします。  
  
```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppArray`  
 ポインター、 **SAFEARRAY**をコピーします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドの内容をコピーする、 **SAFEARRAY**現在`CComSafeArray`オブジェクトです。 配列の既存の内容は置き換えられます。  
  
##  <a name="a-namecopytoa--ccomsafearraycopyto"></a><a name="copyto"></a>CComSafeArray::CopyTo  
 `CComSafeArray` オブジェクトのコピーを作成します。  
  
```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppArray`  
 新しいを作成する場所へのポインター **SAFEARRAY**します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドの内容をコピーする、`CComSafeArray`オブジェクトを**SAFEARRAY**構造体。  
  
##  <a name="a-namecreatea--ccomsafearraycreate"></a><a name="create"></a>CComSafeArray::Create  
 
          `CComSafeArray` を作成します。  
  
```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBound`  
 ポインター、 **SAFEARRAYBOUND**オブジェクトです。  
  
 `uDims`  
 配列の次元の数。  
  
 `ulCount`  
 配列の要素数。  
  
 `lLBound`  
 下限値。つまり、配列の最初の要素のインデックス。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 A `CComSafeArray` 、既存のオブジェクトを作成できる**SAFEARRAYBOUND**構造体、または、配列の下限の境界で要素の数を指定することによって、ディメンションの数。 配列は、Visual C からアクセスするのには、下限が 0 になります。 その他の言語には、その他の値の下限の境界 (-10 ~ 10 などの範囲に要素を持つ Visual の基本的なサポート配列など) ことができます。  
  
##  <a name="a-namedestroya--ccomsafearraydestroy"></a><a name="destroy"></a>CComSafeArray::Destroy  
 `CComSafeArray` オブジェクトを破棄します。  
  
```
HRESULT Destroy();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 既存の破棄`CComSafeArray`オブジェクトとすべてのデータが含まれています。  
  
##  <a name="a-namedetacha--ccomsafearraydetach"></a><a name="detach"></a>CComSafeArray::Detach  
 **オブジェクトから** SAFEARRAY `CComSafeArray` をデタッチします。  
  
```
LPSAFEARRAY Detach();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを返す、 **SAFEARRAY**オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このメソッドはデタッチ、 **SAFEARRAY**オブジェクトから、`CComSafeArray`オブジェクトです。  
  
##  <a name="a-namegetata--ccomsafearraygetat"></a><a name="getat"></a>CComSafeArray::GetAt  
 1 次元配列から&1; つの要素を取得します。  
  
```
T& GetAt(LONG lIndex) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `lIndex`  
 返される配列の値のインデックス番号。  
  
### <a name="return-value"></a>戻り値  
 要求された配列の要素への参照を返します。  
  
##  <a name="a-namegetcounta--ccomsafearraygetcount"></a><a name="getcount"></a>CComSafeArray::GetCount  
 配列内の要素の数を返します。  
  
```
ULONG GetCount(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `uDim`  
 配列の次元。  
  
### <a name="return-value"></a>戻り値  
 配列内の要素の数を返します。  
  
### <a name="remarks"></a>コメント  
 多次元配列を併用すると、このメソッドは特定のディメンションだけで要素の数を返します。  
  
##  <a name="a-namegetdimensionsa--ccomsafearraygetdimensions"></a><a name="getdimensions"></a>CComSafeArray::GetDimensions  
 配列内の次元数を返します。  
  
```
UINT GetDimensions() const;
```  
  
### <a name="return-value"></a>戻り値  
 配列内の次元数を返します。  
  
##  <a name="a-namegetlowerbounda--ccomsafearraygetlowerbound"></a><a name="getlowerbound"></a>CComSafeArray::GetLowerBound  
 配列の指定した次元の下限を返します。  
  
```
LONG GetLowerBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `uDim`  
 下限の境界を取得する対象の配列の次元。 省略した場合、既定値は 0 です。  
  
### <a name="return-value"></a>戻り値  
 下限の境界を返します。  
  
### <a name="remarks"></a>コメント  
 下限が 0 の場合は、この最初の要素は、要素番号 0 C のような配列を示します。 エラーが発生した場合など、無効な次元の引数では、このメソッドを呼び出します`AtlThrow`HRESULT エラーを説明するとします。  
  
##  <a name="a-namegetsafearrayptra--ccomsafearraygetsafearrayptr"></a><a name="getsafearrayptr"></a>CComSafeArray::GetSafeArrayPtr  
 `m_psa` データ メンバーのアドレスを返します。  
  
```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを返す、 [CComSafeArray::m_psa](#m_psa)データ メンバーです。  
  
##  <a name="a-namegettypea--ccomsafearraygettype"></a><a name="gettype"></a>CComSafeArray::GetType  
 配列に格納されているデータの型を返します。  
  
```
VARTYPE GetType() const;
```  
  
### <a name="return-value"></a>戻り値  
 次の種類のいずれかである可能性があると、配列に格納されたデータの種類が返されます。  
  
|VARTYPE|説明|  
|-------------|-----------------|  
|VT_I1|char|  
|VT_I2|short|  
|VT_I4|int|  
|VT_I4|long|  
|VT_I8|longlong|  
|VT_UI1|byte|  
|VT_UI2|ushort|  
|VT_UI4|uint|  
|VT_UI4|ulong|  
|VT_UI8|ulonglong|  
|VT_R4|float|  
|VT_R8|double|  
|VT_DECIMAL|10 進ポインター|  
|VT_VARIANT|バリアント ポインター|  
|VT_CY|Currency データ型|  
  
##  <a name="a-namegetupperbounda--ccomsafearraygetupperbound"></a><a name="getupperbound"></a>CComSafeArray::GetUpperBound  
 配列の任意の次元の上限を返します。  
  
```
LONG GetUpperBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `uDim`  
 上限の境界を取得する対象の配列の次元。 省略した場合、既定値は 0 です。  
  
### <a name="return-value"></a>戻り値  
 上限の境界を返します。 この値は、含んでいるため、このディメンションの有効な最大のインデックス。  
  
### <a name="remarks"></a>コメント  
 エラーが発生した場合など、無効な次元の引数では、このメソッドを呼び出します`AtlThrow`HRESULT エラーを説明するとします。  
  
##  <a name="a-nameissizablea--ccomsafearrayissizable"></a><a name="issizable"></a>CComSafeArray::IsSizable  
 `CComSafeArray` オブジェクトのサイズを変更できるかどうかをテストします。  
  
```
bool IsSizable() const;
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**場合、`CComSafeArray`サイズを変更できる、 **false**できない場合。  
  
##  <a name="a-namempsaa--ccomsafearraympsa"></a><a name="m_psa"></a>CComSafeArray::m_psa  
 アドレスを保持する、 **SAFEARRAY**構造にアクセスします。  
  
```
LPSAFEARRAY m_psa;
```  
  
##  <a name="a-namemultidimgetata--ccomsafearraymultidimgetat"></a><a name="multidimgetat"></a>CComSafeArray::MultiDimGetAt  
 多次元配列から&1; つの要素を取得します。  
  
```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```  
  
### <a name="parameters"></a>パラメーター  
 `alIndex`  
 配列内の各ディメンションのインデックスのベクターへのポインター。 (最上位) の一番左の次元は`alIndex`[0]*します。*  
  
 *t*  
 データへの参照が返されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namemultidimsetata--ccomsafearraymultidimsetat"></a><a name="multidimsetat"></a>CComSafeArray::MultiDimSetAt  
 多次元配列の要素の値を設定します。  
  
```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```  
  
### <a name="parameters"></a>パラメーター  
 `alIndex`  
 配列内の各ディメンションのインデックスのベクターへのポインター。 (最下位) の一番右の次元は`alIndex`[0]。  
  
 *T*  
 新しい要素の値を指定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 これは、多次元のバージョンの[CComSafeArray::SetAt](#setat)します。  
  
##  <a name="a-nameoperatorata--ccomsafearrayoperator-"></a><a name="operator_at"></a>CComSafeArray::operator\[\]  
 配列から要素を取得します。  
  
```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```  
  
### <a name="parameters"></a>パラメーター  
 *lIndex nIndex*  
 配列内の必須の要素のインデックス番号。  
  
### <a name="return-value"></a>戻り値  
 適切な配列の要素を返します。  
  
### <a name="remarks"></a>コメント  
 同様の機能を実行[CComSafeArray::GetAt](#getat)は、この演算子は、1 次元配列でのみ動作します。  
  
##  <a name="a-nameoperatoreqa--ccomsafearrayoperator-"></a><a name="operator_eq"></a>CComSafeArray::operator =  
 代入演算子。  
  
```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `saSrc`  
 `CComSafeArray` オブジェクトへの参照。  
  
 `psaSrc`  
 ポインター、 **SAFEARRAY**オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 配列に格納されているデータの型を返します。  
  
##  <a name="a-nameoperatorlpsafearraya--ccomsafearrayoperator-lpsafearray"></a><a name="operator_lpsafearray"></a>CComSafeArray::operator LPSAFEARRAY  
 値を **SAFEARRAY** ポインターにキャストします。  
  
```
operator LPSAFEARRAY() const;
```  
  
### <a name="return-value"></a>戻り値  
 値を **SAFEARRAY** ポインターにキャストします。  
  
##  <a name="a-nameresizea--ccomsafearrayresize"></a><a name="resize"></a>CComSafeArray::Resize  
 `CComSafeArray` オブジェクトのサイズを変更します。  
  
```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBound`  
 ポインター、 **SAFEARRAYBOUND**要素の数と配列の下限の情報を含む構造体。  
  
 `ulCount`  
 要求されたサイズを変更した配列内のオブジェクト数。  
  
 `lLBound`  
 下限値です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、右端の次元にだけサイズを変更します。 これは、サイズが変更されない配列を返す**IsResizable**として**false**します。  
  
##  <a name="a-namesetata--ccomsafearraysetat"></a><a name="setat"></a>CComSafeArray::SetAt  
 1 次元配列の要素の値を設定します。  
  
```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lIndex`  
 設定する配列要素のインデックス番号。  
  
 *t*  
 指定した要素の新しい値。  
  
 `bCopy`  
 データのコピーを作成するかどうかを示します。 既定値は**TRUE**します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 `bCopy`にフラグが考慮されるときに型の要素`BSTR`または**VARIANT**配列に追加されます。 既定値の**TRUE**により、配列に要素が追加されたときに、データの新しいコピーを作成します。  
  
## <a name="see-also"></a>関連項目  
 [SAFEARRAY データ型](http://msdn.microsoft.com/en-us/9ec8025b-4763-4526-ab45-390c5d8b3b1e)   
 [CComSafeArray::Create](#create)   
 [CComSafeArray::Destroy](#destroy)   
 [クラスの概要](../../atl/atl-class-overview.md)

