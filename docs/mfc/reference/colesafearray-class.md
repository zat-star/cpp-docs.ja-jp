---
title: "使用してクラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleSafeArray
- AFXDISP/COleSafeArray
- AFXDISP/COleSafeArray::COleSafeArray
- AFXDISP/COleSafeArray::AccessData
- AFXDISP/COleSafeArray::AllocData
- AFXDISP/COleSafeArray::AllocDescriptor
- AFXDISP/COleSafeArray::Attach
- AFXDISP/COleSafeArray::Clear
- AFXDISP/COleSafeArray::Copy
- AFXDISP/COleSafeArray::Create
- AFXDISP/COleSafeArray::CreateOneDim
- AFXDISP/COleSafeArray::Destroy
- AFXDISP/COleSafeArray::DestroyData
- AFXDISP/COleSafeArray::DestroyDescriptor
- AFXDISP/COleSafeArray::Detach
- AFXDISP/COleSafeArray::GetByteArray
- AFXDISP/COleSafeArray::GetDim
- AFXDISP/COleSafeArray::GetElement
- AFXDISP/COleSafeArray::GetElemSize
- AFXDISP/COleSafeArray::GetLBound
- AFXDISP/COleSafeArray::GetOneDimSize
- AFXDISP/COleSafeArray::GetUBound
- AFXDISP/COleSafeArray::Lock
- AFXDISP/COleSafeArray::PtrOfIndex
- AFXDISP/COleSafeArray::PutElement
- AFXDISP/COleSafeArray::Redim
- AFXDISP/COleSafeArray::ResizeOneDim
- AFXDISP/COleSafeArray::UnaccessData
- AFXDISP/COleSafeArray::Unlock
dev_langs:
- C++
helpviewer_keywords:
- COleSafeArray class
- arrays [C++], safe
- safe arrays
- ODBC, safe arrays
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3cb6fa49e3adf7e14c34baf7feb64d12e54f2758
ms.lasthandoff: 02/24/2017

---
# <a name="colesafearray-class"></a>使用してクラス
任意の型および次元の配列を扱うクラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class COleSafeArray : public tagVARIANT  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleSafeArray::COleSafeArray](#colesafearray)|`COleSafeArray` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleSafeArray::AccessData](#accessdata)|配列データへのポインターを取得します。|  
|[COleSafeArray::AllocData](#allocdata)|配列のメモリを割り当てます。|  
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|セーフ配列の記述子のメモリを割り当てます。|  
|[COleSafeArray::Attach](#attach)|既存のコントロールは、 **VARIANT**配列を`COleSafeArray`オブジェクトです。|  
|[COleSafeArray::Clear](#clear)|基になるすべてのデータを解放**VARIANT**します。|  
|[COleSafeArray::Copy](#copy)|既存の配列のコピーを作成します。|  
|[COleSafeArray::Create](#create)|セーフ配列を作成します。|  
|[COleSafeArray::CreateOneDim](#createonedim)|1 次元作成`COleSafeArray`オブジェクトです。|  
|[COleSafeArray::Destroy](#destroy)|既存の配列を破棄します。|  
|[COleSafeArray::DestroyData](#destroydata)|セーフ配列内のデータを破棄します。|  
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|セーフ配列の記述子を破棄します。|  
|[COleSafeArray::Detach](#detach)|デタッチ、 **VARIANT**の配列を`COleSafeArray`オブジェクト (をデータには解放されません)。|  
|[COleSafeArray::GetByteArray](#getbytearray)|セーフ配列の内容をコピー、 [CByteArray](../../mfc/reference/cbytearray-class.md)します。|  
|[COleSafeArray::GetDim](#getdim)|配列内の次元数を返します。|  
|[COleSafeArray::GetElement](#getelement)|セーフ配列の&1; つの要素を取得します。|  
|[COleSafeArray::GetElemSize](#getelemsize)|セーフ配列の要素を&1; つのバイト単位のサイズを返します。|  
|[COleSafeArray::GetLBound](#getlbound)|セーフ配列の任意の次元の下限の境界を返します。|  
|[COleSafeArray::GetOneDimSize](#getonedimsize)|1 次元で要素の数を返す`COleSafeArray`オブジェクトです。|  
|[COleSafeArray::GetUBound](#getubound)|セーフ配列の任意の次元の上限の境界を返します。|  
|[COleSafeArray::Lock](#lock)|配列のロック カウントをインクリメントして、配列の記述子の配列のデータへのポインターを格納します。|  
|[COleSafeArray::PtrOfIndex](#ptrofindex)|インデックス付きの要素へのポインターを返します。|  
|[COleSafeArray::PutElement](#putelement)|1 つの要素を配列に割り当てます。|  
|[COleSafeArray::Redim](#redim)|セーフ配列の最下位 (右端) の境界を変更します。|  
|[COleSafeArray::ResizeOneDim](#resizeonedim)|1 次元の要素の数を変更`COleSafeArray`オブジェクトです。|  
|[COleSafeArray::UnaccessData](#unaccessdata)|デクリメント、ロックは、配列のカウントし、によって取得されたポインターを無効に`AccessData`します。|  
|[COleSafeArray::Unlock](#unlock)|ロック カウントをデクリメント配列の解放またはサイズを変更できるようにします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[COleSafeArray::operator LPCVARIANT](#operator_lpcvariant)|基になるにアクセスする**VARIANT**の構造、`COleSafeArray`オブジェクトです。|  
|[COleSafeArray::operator LPVARIANT](#operator_lpvariant)|基になるにアクセスする**VARIANT**の構造、`COleSafeArray`オブジェクトです。|  
|[COleSafeArray::operator =](#operator_eq)|値をコピー、`COleSafeArray`オブジェクト ( **SAFEARRAY**、 **VARIANT**、 `COleVariant`、または`COleSafeArray`配列)。|  
|[COleSafeArray::operator = =](#operator_eq_eq)|2 つのバリアント型の配列を比較 ( **SAFEARRAY**、**バリアント**、 `COleVariant`、または`COleSafeArray`配列)。|  
|[COleSafeArray::operator&lt;&lt;](#operator_lt_lt)|内容を出力する`COleSafeArray`ダンプ コンテキストへのオブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `COleSafeArray`OLE から派生した**VARIANT**構造体。 OLE **SAFEARRAY**メンバー関数から入手`COleSafeArray`とともに、バイトの&1; 次元配列用に設計されたメンバー関数のセットとして。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `tagVARIANT`  
  
 `COleSafeArray`  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="accessdata"></a>COleSafeArray::AccessData  
 配列データへのポインターを取得します。  
  
```  
void AccessData(void** ppvData);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppvData`  
 配列データへのポインターへのポインター。  
  
### <a name="remarks"></a>コメント  
 エラー、関数、[関数](../../mfc/reference/cmemoryexception-class.md)または[関数](../../mfc/reference/coleexception-class.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer #&26;](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]  
  
##  <a name="allocdata"></a>COleSafeArray::AllocData  
 セーフ配列にメモリを割り当てます。  
  
```  
void AllocData();
```  
  
### <a name="remarks"></a>コメント  
 エラー、関数、[関数](../../mfc/reference/cmemoryexception-class.md)または[関数](../../mfc/reference/coleexception-class.md)します。  
  
##  <a name="allocdescriptor"></a>COleSafeArray::AllocDescriptor  
 セーフ配列の記述子のメモリを割り当てます。  
  
```  
void AllocDescriptor(DWORD dwDims);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDims`  
 セーフ配列の次元数。  
  
### <a name="remarks"></a>コメント  
 エラー、関数、[関数](../../mfc/reference/cmemoryexception-class.md)または[関数](../../mfc/reference/coleexception-class.md)します。  
  
##  <a name="attach"></a>COleSafeArray::Attach  
 既存のデータの制御**VARIANT**配列を`COleSafeArray`オブジェクトです。  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *varSrc*  
 A **VARIANT**オブジェクトです。 *VarSrc*パラメーターが必要、 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)**VT_ARRAY**します。  
  
### <a name="remarks"></a>コメント  
 ソース**VARIANT**の種類に設定されて`VT_EMPTY`します。 この関数は、存在する場合に、現在の配列のデータをクリアします。  
  
### <a name="example"></a>例  
  例を参照してください[COleSafeArray::AccessData](#accessdata)します。  
  
##  <a name="clear"></a>COleSafeArray::Clear  
 セーフ配列をクリアします。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>コメント  
 関数では、セーフ配列をクリアするには、`VARTYPE`するオブジェクトの`VT_EMPTY`です。 現在の内容がリリースされ、配列が解放されます。  
  
##  <a name="colesafearray"></a>COleSafeArray::COleSafeArray  
 `COleSafeArray` オブジェクトを構築します。  
  
```  
COleSafeArray();

 
COleSafeArray(
    const SAFEARRAY& saSrc,
    VARTYPE vtSrc);

 
COleSafeArray(
    LPCSAFEARRAY pSrc,
    VARTYPE vtSrc);  
  
COleSafeArray(const COleSafeArray& saSrc);  
COleSafeArray(const VARIANT& varSrc);  
  COleSafeArray(LPCVARIANT pSrc);  
COleSafeArray(const COleVariant& varSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `saSrc`  
 既存の`COleSafeArray`オブジェクトまたは**SAFEARRAY**新しいにコピーされる`COleSafeArray`オブジェクトです。  
  
 `vtSrc`  
 **VARTYPE**新しい`COleSafeArray`オブジェクトです。  
  
 `psaSrc`  
 ポインター、 **SAFEARRAY**新しいにコピーされる`COleSafeArray`オブジェクトです。  
  
 *varSrc*  
 既存の**VARIANT**または`COleVariant`新しいにコピーされるオブジェクト`COleSafeArray`オブジェクトです。  
  
 `pSrc`  
 ポインター、 **VARIANT**新しいにコピーされるオブジェクト`COleSafeArray`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 これらのコンス トラクターのいずれも新しい作成`COleSafeArray`オブジェクトです。 空のパラメーターがない場合は`COleSafeArray`オブジェクトが作成される ( `VT_EMPTY`)。 場合、`COleSafeArray`が別のコピー元の配列[VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)は暗黙的に呼ばれます (、 `COleSafeArray`、 `COleVariant`、または**VARIANT**)、 **VARTYPE**ソースの配列が保持され、指定する必要はありません。 場合、`COleSafeArray`が別のコピー元配列**VARTYPE**が不明 ( **SAFEARRAY**)、 **VARTYPE**で指定する必要があります、`vtSrc`パラメーター。  
  
 エラー、関数、[関数](../../mfc/reference/cmemoryexception-class.md)または[関数](../../mfc/reference/coleexception-class.md)します。  
  
##  <a name="copy"></a>COleSafeArray::Copy  
 既存のセーフ配列のコピーを作成します。  
  
```  
void Copy(LPSAFEARRAY* ppsa);
```  
  
### <a name="parameters"></a>パラメーター  
 *ppsa*  
 新しい配列の記述子を返す場所へのポインター。  
  
### <a name="remarks"></a>コメント  
 エラー、関数、[関数](../../mfc/reference/cmemoryexception-class.md)または[関数](../../mfc/reference/coleexception-class.md)します。  
  
##  <a name="create"></a>COleSafeArray::Create  
 配列にデータを初期化します。  
  
```  
void Create(
    VARTYPE vtSrc,  
    DWORD dwDims,  
    DWORD* rgElements);

 
void Create(
    VARTYPE vtSrc,  
    DWORD dwDims,  
    SAFEARRAYBOUND* rgsabounds);
```  
  
### <a name="parameters"></a>パラメーター  
 `vtSrc`  
 配列の基本型 (つまり、 **VARTYPE**配列の各要素)。 **VARTYPE** variant 型のサブセットに制限されます。 どちらも、 **VT_ARRAY**も**VT_BYREF**フラグを設定することができます。 `VT_EMPTY`**VT_**配列の有効な基本型ではありません。 その他のすべての種類は有効です。  
  
 `dwDims`  
 配列の次元の数。 これは、配列の作成後[Redim](#redim)します。  
  
 *rgElements*  
 配列内の各ディメンションの要素の数の配列へのポインター。  
  
 *rgsabounds*  
 境界 (ディメンションごとに&1; つ) のベクターへのポインター、配列を割り当てられません。  
  
### <a name="remarks"></a>コメント  
 この関数は、必要に応じて、現在の配列のデータがクリアされます。 エラー、関数、[関数](../../mfc/reference/cmemoryexception-class.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer #&27;](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="createonedim"></a>COleSafeArray::CreateOneDim  
 新しい&1; 次元`COleSafeArray`オブジェクトです。  
  
```  
void CreateOneDim(
    VARTYPE vtSrc,  
    DWORD dwElements,  
    const void* pvSrcData = NULL,  
    long nLBound = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `vtSrc`  
 配列の基本型 (つまり、 **VARTYPE**配列の各要素)。  
  
 `dwElements`  
 配列内の要素の数。 これは、配列の作成後[でも](#resizeonedim)します。  
  
 `pvSrcData`  
 配列にコピーするデータへのポインター。  
  
 *nLBound*  
 配列の下限値です。  
  
### <a name="remarks"></a>コメント  
 関数は、場合に、指定されたデータをコピーして、配列のデータの初期化ポインター`pvSrcData`は**NULL**します。  
  
 エラー、関数、[関数](../../mfc/reference/cmemoryexception-class.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer #&28;](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]  
  
##  <a name="destroy"></a>COleSafeArray::Destroy  
 既存の配列の記述子と配列内のすべてのデータを破棄します。  
  
```  
void Destroy();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトが配列に格納されている場合は、各オブジェクトが解放されます。 エラー、関数、[関数](../../mfc/reference/cmemoryexception-class.md)または[関数](../../mfc/reference/coleexception-class.md)します。  
  
##  <a name="destroydata"></a>COleSafeArray::DestroyData  
 セーフ配列内のすべてのデータを破棄します。  
  
```  
void DestroyData();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトが配列に格納されている場合は、各オブジェクトが解放されます。 エラー、関数、[関数](../../mfc/reference/cmemoryexception-class.md)または[関数](../../mfc/reference/coleexception-class.md)します。  
  
##  <a name="destroydescriptor"></a>COleSafeArray::DestroyDescriptor  
 セーフ配列の記述子を破棄します。  
  
```  
void DestroyDescriptor();
```  
  
### <a name="remarks"></a>コメント  
 エラー、関数、[関数](../../mfc/reference/cmemoryexception-class.md)または[関数](../../mfc/reference/coleexception-class.md)します。  
  
##  <a name="detach"></a>COleSafeArray::Detach  
 デタッチ、 **VARIANT**からデータを`COleSafeArray`オブジェクトです。  
  
```  
VARIANT Detach();
```  
  
### <a name="return-value"></a>戻り値  
 基になる**VARIANT**内の値、`COleSafeArray`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 関数では、セーフ配列内のデータをデタッチを設定して、 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)するオブジェクトの`VT_EMPTY`です。 Windows の関数を呼び出すことによって、配列を解放する呼び出し元の役目です[VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835)します。  
  
 エラー、関数、[関数](../../mfc/reference/coleexception-class.md)します。  
  
### <a name="example"></a>例  
  例を参照してください[COleSafeArray::PutElement](#putelement)します。  
  
##  <a name="getbytearray"></a>COleSafeArray::GetByteArray  
 セーフ配列の内容をコピー、`CByteArray`です。  
  
```  
void GetByteArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>パラメーター  
 `bytes`  
 参照、 [CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクトです。  
  
##  <a name="getdim"></a>COleSafeArray::GetDim  
 次元数を返す、`COleSafeArray`オブジェクトです。  
  
```  
DWORD GetDim();
```  
  
### <a name="return-value"></a>戻り値  
 セーフ配列の次元数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer #&27;](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="getelement"></a>COleSafeArray::GetElement  
 セーフ配列の&1; つの要素を取得します。  
  
```  
void GetElement(
    long* rgIndices,  
    void* pvData);
```  
  
### <a name="parameters"></a>パラメーター  
 `rgIndices`  
 インデックスの配列へのポインター (配列の次元ごと)。  
  
 `pvData`  
 配列の要素を配置する場所へのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数は、windows の関数を自動的に呼び出します`SafeArrayLock`と`SafeArrayUnlock`前に、と後、要素を取得します。 データ要素が文字列、オブジェクト、またはバリアントの場合は、関数は、適切な方法で要素をコピーします。 パラメーター`pvData`要素を格納するための十分なバッファー サイズの大きいをポイントする必要があります。  
  
 エラー、関数、[関数](../../mfc/reference/cmemoryexception-class.md)または[関数](../../mfc/reference/coleexception-class.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer #&29;](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]  
  
##  <a name="getelemsize"></a>COleSafeArray::GetElemSize  
 内の要素のサイズを取得、`COleSafeArray`オブジェクトです。  
  
```  
DWORD GetElemSize();
```  
  
### <a name="return-value"></a>戻り値  
 セーフ配列の要素のバイト単位のサイズ。  
  
##  <a name="getlbound"></a>COleSafeArray::GetLBound  
 任意の次元の下限の境界を返す、`COleSafeArray`オブジェクトです。  
  
```  
void GetLBound(
    DWORD dwDim,  
    long* pLBound);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDim`  
 下限の境界を取得する対象の配列の次元。  
  
 *pLBound*  
 下限の境界を返す場所へのポインター。  
  
### <a name="remarks"></a>コメント  
 エラー、関数、[関数](../../mfc/reference/coleexception-class.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer #&30;](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]  
  
##  <a name="getonedimsize"></a>COleSafeArray::GetOneDimSize  
 1 次元で要素の数を返す`COleSafeArray`オブジェクトです。  
  
```  
DWORD GetOneDimSize();
```  
  
### <a name="return-value"></a>戻り値  
 1 次元のセーフ配列の要素の数。  
  
### <a name="example"></a>例  
  例を参照してください[COleSafeArray::CreateOneDim](#createonedim)します。  
  
##  <a name="getubound"></a>COleSafeArray::GetUBound  
 セーフ配列の任意の次元の上限の境界を返します。  
  
```  
void GetUBound(
    DWORD dwDim,  
    long* pUBound);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDim`  
 上限の境界を取得する対象の配列の次元。  
  
 *pUBound*  
 上限の境界を返す場所へのポインター。  
  
### <a name="remarks"></a>コメント  
 エラー、関数、[関数](../../mfc/reference/coleexception-class.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer #&31;](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]  
  
##  <a name="lock"></a>COleSafeArray::Lock  
 配列、配列の記述子の配列のデータへのポインターの場所のロック カウントをインクリメントします。  
  
```  
void Lock();
```  
  
### <a name="remarks"></a>コメント  
 スローしてエラーが発生した、[関数](../../mfc/reference/coleexception-class.md)します。  
  
 配列の記述子のポインターの有効期限`Unlock`が呼び出されます。 呼び出す`Lock`ネストできますへの呼び出しの数が等しい`Unlock`が必要です。  
  
 ロック中に、配列を削除できません。  
  
##  <a name="operator_lpcvariant"></a>COleSafeArray::operator LPCVARIANT  
 このキャスト演算子を呼び出す**VARIANT**この構造体`COleSafeArray`オブジェクトです。  
  
```  
operator LPCVARIANT() const;  
```  
  
##  <a name="operator_lpvariant"></a>COleSafeArray::operator LPVARIANT  
 このキャスト演算子を呼び出す**VARIANT**この構造体`COleSafeArray`オブジェクトです。  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>コメント  
 値を変更することに注意してください、 **VARIANT**構造体がこの関数によって返されるポインターではこの値を変更`COleSafeArray`オブジェクトです。  
  
##  <a name="operator_eq"></a>COleSafeArray::operator =  
 これらのオーバー ロード代入演算子はコピー元の値をこの`COleSafeArray`オブジェクトです。  
  
```  
COleSafeArray& operator=(const COleSafeArray& saSrc);  
COleSafeArray& operator=(const VARIANT& varSrc);  
  COleSafeArray& operator=(LPCVARIANT pSrc);  
COleSafeArray& operator=(const COleVariant& varSrc);
```  
  
### <a name="remarks"></a>コメント  
 各演算子の簡単な説明に従います。  
  
- **operator = (** *saSrc* **)** 、既存のコピー`COleSafeArray`オブジェクトをこのオブジェクトにします。  
  
- **演算子 = (** *varSrc***)** 、既存のコピー **VARIANT**または`COleVariant`このオブジェクトの配列。  
  
- **演算子 = (** `pSrc` **)**コピー、 **VARIANT**からアクセスされるオブジェクトの配列`pSrc`このオブジェクトにします。  
  
##  <a name="operator_eq_eq"></a>COleSafeArray::operator = =  
 この演算子は、2 つの配列を比較 ( **SAFEARRAY**、 **VARIANT**、 `COleVariant`、または`COleSafeArray`配列) し、それらは同一です。 それ以外の場合 0 の場合は 0 以外を返します。  
  
```  
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;  
   
BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;  
   
BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;  ```  
  
### Remarks  
 Two arrays are equal if they have an equal number of dimensions, equal size in each dimension, and equal element values.  
  
##  <a name="operator_lt_lt"></a>  COleSafeArray::operator &lt;&lt;  
 The `COleSafeArray` insertion (<<) operator supports diagnostic dumping and storing of a `COleSafeArray` object to an archive.  
  
```  
CDumpContext >/documents/report1.rdl」の AFXAPI 演算子<( CDumpContext& dc, cdumpcontext&=""></( CDumpContext& dc,>  
    使用して >/reportbuilder/reportbuilder_3_0_0_0.application saSrc) です。
```  
  
##  <a name="ptrofindex"></a>  COleSafeArray::PtrOfIndex  
 Returns a pointer to the element specified by the index values.  
  
```  
PtrOfIndex を無効にする (長い*返す時、void** ppvData) です。
```  
  
### Parameters  
 `rgIndices`  
 An array of index values that identify an element of the array. All indexes for the element must be specified.  
  
 `ppvData`  
 On return, pointer to the element identified by the values in `rgIndices`.  
  
##  <a name="putelement"></a>  COleSafeArray::PutElement  
 Assigns a single element into the array.  
  
```  
PutElement を無効にする (長い*返す時、void* pvData) です。
```  
  
### Parameters  
 `rgIndices`  
 Pointer to an array of indexes for each dimension of the array.  
  
 `pvData`  
 Pointer to the data to assign to the array. **VT_DISPATCH**, **VT_UNKNOWN**, and `VT_BSTR` variant types are pointers and do not require another level of indirection.  
  
### Remarks  
 This function automatically calls the Windows functions [SafeArrayLock](https://msdn.microsoft.com/library/windows/desktop/ms221492.aspx) and [SafeArrayUnlock](https://msdn.microsoft.com/library/windows/desktop/ms221246.aspx) before and after assigning the element. If the data element is a string, object, or variant, the function copies it correctly, and if the existing element is a string, object, or variant, it is cleared correctly.  
  
 Note that you can have multiple locks on an array, so you can put elements into an array while the array is locked by other operations.  
  
 On error, the function throws a [CMemoryException](../../mfc/reference/cmemoryexception-class.md) or [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
 [!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]  
  
##  <a name="redim"></a>  COleSafeArray::Redim  
 Changes the least significant (rightmost) bound of a safe array.  
  
```  
redim ステートメント (SAFEARRAYBOUND * psaboundNew); を無効にします。
```  
  
### Parameters  
 *psaboundNew*  
 Pointer to a new safe array bound structure containing the new array bound. Only the least significant dimension of an array may be changed.  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="resizeonedim"></a>  COleSafeArray::ResizeOneDim  
 Changes the number of elements in a one-dimensional `COleSafeArray` object.  
  
```  
void でも (DWORD dwElements) です。
```  
  
### Parameters  
 `dwElements`  
 Number of elements in the one-dimensional safe array.  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
  See the example for [COleSafeArray::CreateOneDim](#createonedim).  
  
##  <a name="unaccessdata"></a>  COleSafeArray::UnaccessData  
 Decrements the lock count of an array and invalidates the pointer retrieved by `AccessData`.  
  
```  
UnaccessData(); を無効にします。
```  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
  See the example for [COleSafeArray::AccessData](#accessdata).  
  
##  <a name="unlock"></a>  COleSafeArray::Unlock  
 Decrements the lock count of an array so it can be freed or resized.  
  
```  
Unlock(); を無効にします。
```  
  
### Remarks  
 This function is called after access to the data in an array is finished. On error, it throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
## See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)

