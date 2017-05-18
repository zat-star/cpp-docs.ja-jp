---
title: "COleVariant クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleVariant
- AFXDISP/COleVariant
- AFXDISP/COleVariant::COleVariant
- AFXDISP/COleVariant::Attach
- AFXDISP/COleVariant::ChangeType
- AFXDISP/COleVariant::Clear
- AFXDISP/COleVariant::Detach
- AFXDISP/COleVariant::GetByteArrayFromVariantArray
- AFXDISP/COleVariant::SetString
dev_langs:
- C++
helpviewer_keywords:
- Automation, parameter types
- COleVariant class
- VARIANT data type
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
caps.latest.revision: 24
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
ms.openlocfilehash: 753566adc5fc8e48ad31da52c2bb3f04c9e21727
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="colevariant-class"></a>COleVariant クラス
カプセル化、 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)データ型。  
  
## <a name="syntax"></a>構文  
  
```  
class COleVariant : public tagVARIANT  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleVariant::COleVariant](#colevariant)|`COleVariant` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleVariant::Attach](#attach)|アタッチ、 **VARIANT**に、`COleVariant`です。|  
|[COleVariant::ChangeType](#changetype)|このバリアント型を変更`COleVariant`オブジェクトです。|  
|[COleVariant::Clear](#clear)|これをクリア`COleVariant`オブジェクトです。|  
|[COleVariant::Detach](#detach)|デタッチ、 **VARIANT**から、`COleVariant`返します、 **VARIANT**します。|  
|[COleVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|既存の配列からバイト配列を取得します。|  
|[COleVariant::SetString](#setstring)|文字列を ANSI では通常、特定の型に設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[COleVariant::operator LPCVARIANT](#operator_lpcvariant)|変換、`COleVariant`値を`LPCVARIANT`です。|  
|[COleVariant::operator LPVARIANT](#operator_lpvariant)|変換、`COleVariant`オブジェクトを`LPVARIANT`です。|  
|[COleVariant::operator =](#operator_eq)|コピー、`COleVariant`値。|  
|[COleVariant::operator = =](#operator_eq_eq)|2 つを比較して`COleVariant`値。|  
|[COleVariant::operator &lt; &lt;、&gt;&gt;](#operator_lt_lt__gt_gt)|出力、`COleVariant`値を`CArchive`または`CDumpContext`を入力し、`COleVariant`オブジェクトから`CArchive`します。|  
  
## <a name="remarks"></a>コメント  
 このデータ型は OLE オートメーションで使用されます。 具体的には、 [DISPPARAMS](http://msdn.microsoft.com/en-us/a16e5a21-766e-4287-b039-13429aa78f8b)構造体の配列へのポインターを格納する**VARIANT**構造体。 A **DISPPARAMS**にパラメーターを渡す構造体を使用[idispatch::invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d)します。  
  
> [!NOTE]
>  このクラスから派生、 **VARIANT**構造体。 つまり、渡すことができます、`COleVariant`の呼び出しをパラメーターで、 **VARIANT**とのデータ メンバー、 **VARIANT**構造のアクセス可能なデータ メンバーである`COleVariant`です。  
  
 MFC クラスを関連する、2 つ[COleCurrency](../../mfc/reference/colecurrency-class.md)と[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)variant データ型をカプセル化**通貨**( `VT_CY`) と**日付**( `VT_DATE`)。 `COleVariant`クラスは、DAO クラスで広く使用されます。 これらのクラスをこのクラスの一般的な使用を次に例を参照してください[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)と[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)します。  
  
 詳細については、次を参照してください。、 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)、[通貨](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)、 [DISPPARAMS](http://msdn.microsoft.com/en-us/a16e5a21-766e-4287-b039-13429aa78f8b)、および[idispatch::invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d)内のエントリ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 詳細については、`COleVariant`クラスおよび OLE オートメーションでの使用、記事の「オートメーション パラメーターの受け渡しで」を参照して[オートメーション](../../mfc/automation.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `tagVARIANT`  
  
 `COleVariant`  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="attach"></a>COleVariant::Attach  
 アタッチするには、この関数を呼び出す、指定された[VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)現在オブジェクト`COleVariant`オブジェクトです。  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *varSrc*  
 既存の**VARIANT**オブジェクトに現在アタッチされている`COleVariant`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 この関数を設定、 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)の*varSrc*に`VT_EMPTY`します。  
  
 詳細については、次を参照してください。、 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)と[VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)内のエントリ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="colevariant"></a>COleVariant::COleVariant  
 `COleVariant` オブジェクトを構築します。  
  
```  
COleVariant(); 
COleVariant(const VARIANT& varSrc); 
COleVariant(const COleVariant& varSrc); 
COleVariant(LPCVARIANT pSrc); 
COleVariant(LPCTSTR lpszSrc); 
COleVariant(LPCTSTR lpszSrc, VARTYPE vtSrc); 
COleVariant(CString& strSrc); 
COleVariant(BYTE nSrc); 
COleVariant(short nSrc, VARTYPE vtSrc = VT_I2); 
COleVariant(long lSrc,VARTYPE vtSrc = VT_I4); 
COleVariant(const COleCurrency& curSrc); 
COleVariant(float fltSrc); 
COleVariant(double dblSrc); 
COleVariant(const COleDateTime& timeSrc); 
COleVariant(const CByteArray& arrSrc); 
COleVariant(const CLongBinary& lbSrc); 
COleVariant(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>パラメーター  
 *varSrc*  
 既存の`COleVariant`または**VARIANT**新しいにコピーされるオブジェクト`COleVariant`オブジェクトです。  
  
 `pSrc`  
 ポインター、 **VARIANT**新しいにコピーされるオブジェクト`COleVariant`オブジェクトです。  
  
 `lpszSrc`  
 新しいにコピーされる null で終わる文字列`COleVariant`オブジェクトです。  
  
 `vtSrc`  
 `VARTYPE`新しい`COleVariant`オブジェクトです。  
  
 `strSrc`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)新しいにコピーされるオブジェクト`COleVariant`オブジェクトです。  
  
 `nSrc`, `lSrc`  
 新しい `COleVariant` オブジェクトにコピーされる数値。  
  
 `vtSrc`  
 `VARTYPE`新しい`COleVariant`オブジェクトです。  
  
 `curSrc`  
 A [COleCurrency](../../mfc/reference/colecurrency-class.md)新しいにコピーされるオブジェクト`COleVariant`オブジェクトです。  
  
 `fltSrc`, `dblSrc`  
 新しい `COleVariant` オブジェクトにコピーされる数値。  
  
 `timeSrc`  
 A[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)新しいにコピーされるオブジェクト`COleVariant`オブジェクトです。  
  
 `arrSrc`  
 A [CByteArray](../../mfc/reference/cbytearray-class.md)新しいにコピーされるオブジェクト`COleVariant`オブジェクトです。  
  
 `lbSrc`  
 A [CLongBinary](../../mfc/reference/clongbinary-class.md)新しいにコピーされるオブジェクト`COleVariant`オブジェクトです。  
  
 `pidl`  
 ポインター、 [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321)新しいにコピーされる構造`COleVariant`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 これらすべてのコンス トラクターが新規作成`COleVariant`指定した値に初期化されたオブジェクト。 これらのコンス トラクターのそれぞれの簡単な説明が続きます。  
  
- **COleVariant ()** 、空の作成`COleVariant`オブジェクト、`VT_EMPTY`です。  
  
- **COleVariant (** *varSrc* **)** 、既存のコピー **VARIANT**または`COleVariant`オブジェクトです。 バリアント型は保持されます。  
  
- **COleVariant (** `pSrc` **)** 、既存のコピー **VARIANT**または`COleVariant`オブジェクトです。 バリアント型は保持されます。  
  
- **COleVariant (** `lpszSrc` **)**が新しいオブジェクトに文字列をコピー `VT_BSTR` (UNICODE)。  
  
- **COleVariant (** `lpszSrc` **、** `vtSrc` **)**が新しいオブジェクトに文字列をコピーします。 パラメーター`vtSrc`する必要があります`VT_BSTR`(UNICODE) または`VT_BSTRT`(ANSI) です。  
  
- **COleVariant (** `strSrc` **)**が新しいオブジェクトに文字列をコピー **VT_BSTR** (UNICODE)。  
  
- **COleVariant (** `nSrc` **)**を 8 ビット整数を新しいオブジェクトにコピー`VT_UI1`します。  
  
- **COleVariant (** `nSrc` **、** `vtSrc` **)**が新しいオブジェクトに 16 ビット整数 (またはブール値) にコピーします。 パラメーター`vtSrc`する必要があります`VT_I2`または`VT_BOOL`です。  
  
- **COleVariant (** `lSrc` **、** `vtSrc` **)** 32 ビット整数のコピー (または`SCODE`値) が新しいオブジェクトにします。 パラメーター`vtSrc`する必要があります`VT_I4`、 `VT_ERROR`、または`VT_BOOL`です。  
  
- **COleVariant (** `curSrc` **)**コピー、 **COleCurrency**が新しいオブジェクトに値`VT_CY`です。  
  
- **COleVariant (** `fltSrc` **)**が新しいオブジェクトに、32 ビット浮動小数点値をコピー`VT_R4`します。  
  
- **COleVariant (** `dblSrc` **)**が新しいオブジェクトに、64 ビット浮動小数点値をコピー`VT_R8`します。  
  
- **COleVariant (** `timeSrc` **)**コピー、`COleDateTime`が新しいオブジェクトに値`VT_DATE`です。  
  
- **COleVariant (** `arrSrc` **)**コピー、`CByteArray`が新しいオブジェクトにオブジェクト`VT_EMPTY`します。  
  
- **COleVariant (** `lbSrc` **)**コピー、`CLongBinary`が新しいオブジェクトにオブジェクト`VT_EMPTY`します。  
  
 詳細については`SCODE`を参照してください[COM エラー コードの構造体](http://msdn.microsoft.com/library/windows/desktop/ms690088)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="changetype"></a>COleVariant::ChangeType  
 このバリアント型の値の型を変換`COleVariant`オブジェクトです。  
  
```  
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `vartype`  
 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)この`COleVariant`オブジェクトです。  
  
 `pSrc`  
 ポインター、 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)変換するオブジェクト。 この値が場合**NULL**、この`COleVariant`オブジェクトは、変換のソースとして使用します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。、 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)、 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)、および[VariantChangeType](http://msdn.microsoft.com/en-us/48a51e32-95d7-4eeb-8106-f5043ffa2fd1)内のエントリ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="clear"></a>COleVariant::Clear  
 消去、 **VARIANT**します。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>コメント  
 これにより設定、 **VARTYPE**にこのオブジェクトの`VT_EMPTY`です。 `COleVariant`この関数はデストラクターを呼び出します。  
  
 詳細については、次を参照してください。、 `VARIANT`、 `VARTYPE`、および`VariantClear`内のエントリ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="detach"></a>COleVariant::Detach  
 基になるをデタッチ[VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)オブジェクトからこの`COleVariant`オブジェクトです。  
  
```  
VARIANT Detach();
```  
  
### <a name="remarks"></a>コメント  
 この関数を設定、 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)この`COleVariant`オブジェクトを`VT_EMPTY`します。  
  
> [!NOTE]
>  呼び出した後**デタッチ**を呼び出す呼び出し元の役目です**VariantClear** 、その結果に**VARIANT**構造体。  
  
 詳細については、次を参照してください。、 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)、 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)、および[VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835)内のエントリ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getbytearrayfromvariantarray"></a>COleVariant::GetByteArrayFromVariantArray  
 既存の配列からバイト配列を取得します。  
  
```  
void GetByteArrayFromVariantArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>パラメーター  
 `bytes`  
 既存への参照を[CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクトです。  
  
##  <a name="operator_lpcvariant"></a>COleVariant::operator LPCVARIANT  
 このキャスト演算子、`VARIANT`構造体の値がこれからコピー`COleVariant`オブジェクトです。  
  
```  
operator LPCVARIANT() const; 
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="operator_lpvariant"></a>COleVariant::operator LPVARIANT  
 このキャスト演算子を呼び出す`VARIANT`この構造体`COleVariant`オブジェクトです。  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>コメント  
  
> [!CAUTION]
>  値を変更、 **VARIANT**構造体がこの関数によって返されるポインターではこの値を変更`COleVariant`オブジェクトです。  
  
##  <a name="operator_eq"></a>COleVariant::operator =  
 これらのオーバー ロード代入演算子はコピー元の値をこの`COleVariant`オブジェクトです。  
  
```  
const COleVariant& operator=(const VARIANT& varSrc); 
const COleVariant& operator=(LPCVARIANT pSrc); 
const COleVariant& operator=(const COleVariant& varSrc); 
const COleVariant& operator=(const LPCTSTR lpszSrc);
const COleVariant& operator=(const CString& strSrc); 
const COleVariant& operator=(BYTE nSrc); 
const COleVariant& operator=(short nSrc); 
const COleVariant& operator=(long lSrc); 
const COleVariant& operator=(const COleCurrency& curSrc); 
const COleVariant& operator=(float fltSrc); 
const COleVariant& operator=(double dblSrc); 
const COleVariant& operator=(const COleDateTime& dateSrc); 
const COleVariant& operator=(const CByteArray& arrSrc); 
const COleVariant& operator=(const CLongBinary& lbSrc);
```  
  
### <a name="remarks"></a>コメント  
 各演算子の簡単な説明に従います。  
  
- **演算子 = (** *varSrc***)** 、既存のコピー **VARIANT**または`COleVariant`オブジェクトをこのオブジェクトにします。  
  
- **演算子 = (** `pSrc` **)**コピー、 **VARIANT**からアクセスされるオブジェクト`pSrc`このオブジェクトにします。  
  
- **operator = (** `lpszSrc` **)**このオブジェクトに null で終わる文字列をコピーし、設定、 **VARTYPE**に`VT_BSTR`します。  
  
- **演算子 = (** `strSrc` **)**コピー、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトをこのオブジェクトと設定、 **VARTYPE**に`VT_BSTR`します。  
  
- **operator = (** `nSrc` **)** 8 ビットまたは 16 ビット整数値をこのオブジェクトにコピーします。 場合`nSrc`、8 ビット値には、 **VARTYPE**このに設定されている`VT_UI1`します。 場合`nSrc`16 ビット値は、および**VARTYPE**このは`VT_BOOL`、保持している以外の場合に設定されている`VT_I2`します。  
  
- **operator = (** `lSrc` **)** 32 ビット整数値をこのオブジェクトにコピーします。 場合、 **VARTYPE**このは`VT_ERROR`、保持している以外の場合に設定されている`VT_I4`します。  
  
- **演算子 = (** `curSrc` **)**コピー、 [COleCurrency](../../mfc/reference/colecurrency-class.md)をこのオブジェクトとセットのオブジェクト、 **VARTYPE**に`VT_CY`します。  
  
- **operator = (** `fltSrc` **)** 32 ビットの浮動小数点値をこのオブジェクトにコピーし、設定、 **VARTYPE**に`VT_R4`します。  
  
- **operator = (** `dblSrc` **)** 64 ビットの浮動小数点値をこのオブジェクトにコピーし、設定、 **VARTYPE**に`VT_R8`します。  
  
- **演算子 = (** `dateSrc` **)**コピー、[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトをこのオブジェクトと設定、 **VARTYPE**に`VT_DATE`します。  
  
- **演算子 = (** `arrSrc` **)**コピー、 [CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクトをこの`COleVariant`オブジェクトです。  
  
- **演算子 = (** `lbSrc` **)**コピー、 [CLongBinary](../../mfc/reference/clongbinary-class.md)オブジェクトをこの`COleVariant`オブジェクトです。  
  
 詳細については、次を参照してください。、 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)と[VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)内のエントリ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="operator_eq_eq"></a>COleVariant::operator = =  
 この演算子は、2 つのバリアント値を比較し、それらが等しい場合は 0 以外を返しますそれ以外の場合 0 を返します。  
  
```  
BOOL operator==(const VARIANT& varSrc) const; 
BOOL operator==(LPCVARIANT pSrc) const;
```  
  
##  <a name="operator_lt_lt__gt_gt"></a>COleVariant::operator &lt; &lt;、&gt;&gt;  
 出力、`COleVariant`値を`CArchive`または**CdumpContext**を入力し、`COleVariant`オブジェクトから`CArchive`します。  
  
```  
friend CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,  
    OleVariant varSrc);
 
friend CArchive& AFXAPI operator<<(
    CArchive& ar,  
    COleVariant varSrc);
 
friend CArchive& AFXAPI operator>>(
    CArchive& ar,  
    COleVariant& varSrc);
```  
  
### <a name="remarks"></a>コメント  
 `COleVariant`カーソル ( ** < \< **) 演算子は、診断のダンプとアーカイブに格納することをサポートしています。 抽出 ( ** >> **) 演算子は、アーカイブからの読み込みをサポートしています。  
  
##  <a name="setstring"></a>COleVariant::SetString  
 特定の型に文字列を設定します。  
  
```  
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSrc`  
 新しいにコピーされる null で終わる文字列`COleVariant`オブジェクトです。  
  
 *VtSrc*  
 **VARTYPE**新しい`COleVariant`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 パラメーター`vtSrc`する必要があります`VT_BSTR`(UNICODE) または`VT_BSTRT`(ANSI) です。 `SetString`既定値から文字列を ANSI に設定するのには、通常使用、 [COleVariant::COleVariant](#colevariant)の文字列または文字列ポインター パラメーターなしのコンス トラクター **VARTYPE**は UNICODE です。  
  
 UNICODE 以外のビルドにおける DAO レコード セットは、文字列を ansi を想定しています。 したがって、DAO に使用する関数`COleVariant`UNICODE レコード セットを作成していない場合、オブジェクトが使用する必要があります、 **COleVariant::COleVariant (** `lpszSrc` **、** `vtSrc` **)**形式を持つコンス トラクターの`vtSrc`に設定`VT_BSTRT`(ANSI) を使用して、または`SetString`と`vtSrc`に設定`VT_BSTRT`ANSI 文字列の作成にします。 たとえば、`CDaoRecordset`関数[CDaoRecordset::Seek](../../mfc/reference/cdaorecordset-class.md#seek)と[たび](../../mfc/reference/cdaorecordset-class.md#setfieldvalue)を使用して`COleVariant`パラメーターとしてオブジェクトです。 DAO レコード セットが UNICODE でない場合は、これらのオブジェクトを ANSI にあります。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)




