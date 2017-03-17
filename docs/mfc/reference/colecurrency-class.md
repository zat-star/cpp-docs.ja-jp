---
title: "COleCurrency クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleCurrency
- AFXDISP/COleCurrency
- AFXDISP/COleCurrency::COleCurrency
- AFXDISP/COleCurrency::Format
- AFXDISP/COleCurrency::GetStatus
- AFXDISP/COleCurrency::ParseCurrency
- AFXDISP/COleCurrency::SetCurrency
- AFXDISP/COleCurrency::SetStatus
- AFXDISP/COleCurrency::m_cur
- AFXDISP/COleCurrency::m_status
dev_langs:
- C++
helpviewer_keywords:
- fixed-point numbers
- numbers, fixed-point
- CURRENCY
- COleCurrency class
ms.assetid: 3a36e345-303f-46fb-a57c-858274378a8d
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 38dbd45818f53430db37bb5807c255494c4a9896
ms.lasthandoff: 02/24/2017

---
# <a name="colecurrency-class"></a>COleCurrency クラス
OLE オートメーションで使用される `CURRENCY` データ型をカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleCurrency  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleCurrency::COleCurrency](#colecurrency)|`COleCurrency` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleCurrency::Format](#format)|書式設定された文字列表記を生成、`COleCurrency`オブジェクトです。|  
|[COleCurrency::GetStatus](#getstatus)|この状態 (有効) を取得`COleCurrency`オブジェクトです。|  
|[COleCurrency::ParseCurrency](#parsecurrency)|読み取り、**通貨**文字列から値の値を設定および`COleCurrency`です。|  
|[COleCurrency::SetCurrency](#setcurrency)|この値を設定`COleCurrency`オブジェクトです。|  
|[COleCurrency::SetStatus](#setstatus)|この状態 (有効) を設定`COleCurrency`オブジェクトです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[演算子 =](#operator_eq)|コピー、`COleCurrency`値。|  
|[演算子 +、-](#operator_plus_minus)|追加、減算、およびの符号が変わる`COleCurrency`値。|  
|[演算子 + =、=](#operator_plus_minus_eq)|追加し、減算、`COleCurrency`これから値`COleCurrency`オブジェクトです。|  
|[演算子 */](#operator_star)|スケール、`COleCurrency`の値を整数値。|  
|[演算子 * =、/、=](#operator_star_div_eq)|この拡張`COleCurrency`の値を整数値。|  
|[演算子](#operator_stream)|出力、`COleCurrency`値を`CArchive`または`CDumpContext`です。|  
|[演算子 >>](#operator_stream)|入力、`COleCurrency`からオブジェクト`CArchive`します。|  
|[演算子の通貨](#operator_currency)|変換、`COleCurrency`値を**通貨**します。|  
|[演算子 = =、<,></,><=,></=,>](#colecurrency_relational_operators)|2 つを比較して`COleCurrency`値。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleCurrency::m_cur](#m_cur)|基になるを含む**通貨**この`COleCurrency`オブジェクトです。|  
|[COleCurrency::m_status](#m_status)|この状態を表す`COleCurrency`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 **COleCurrency**基本クラスではありません。  
  
 **通貨**は 8 バイト、2 の補数整数の値が 10,000 を掛けとして実装します。 これは、15 桁の整数部と 4 桁の小数部を持つ固定小数点数として表現されます。 **通貨**精度が重要となるデータ型は関連する計算、またはいずれかの固定小数点の計算に非常に便利です。 使用できる型のいずれか、 `VARIANT` OLE オートメーションのデータ型。  
  
 **COleCurrency**もいくつかの基本的な算術演算この固定小数点型を実装します。 サポートされる操作は、固定小数点の計算中に発生する丸め誤差を制御する選択されています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `COleCurrency`  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="colecurrency"></a>COleCurrency::COleCurrency  
 構築、 **COleCurrency**オブジェクトです。  
  
```  
COleCurrency();  
COleCurrency(CURRENCY cySrc);  
  COleCurrency(const COleCurrency& curSrc);  
COleCurrency(const VARIANT& varSrc);

 
COleCurrency(
    long nUnits,  
    long nFractionalUnits);
```  
  
### <a name="parameters"></a>パラメーター  
 `cySrc`  
 A**通貨**新しいにコピーされる値**COleCurrency**オブジェクトです。  
  
 `curSrc`  
 既存の**COleCurrency**新しいにコピーされるオブジェクト**COleCurrency**オブジェクトです。  
  
 *varSrc*  
 既存の**VARIANT**データ構造体 (可能性があります、`COleVariant`オブジェクト) 通貨の値に変換する ( `VT_CY`) し、新しいコピー **COleCurrency**オブジェクトです。  
  
 `nUnits`, `nFractionalUnits`  
 新しいにコピーされる単位および小数部の部分 (1/10 で、000's) の値を示す**COleCurrency**オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 これらのコンス トラクターのいずれも新しい作成**COleCurrency**オブジェクトの指定した値に初期化します。 これらのコンス トラクターのそれぞれの簡単な説明が続きます。 明記されない限り、新しい状態**COleCurrency**項目は、有効な設定です。  
  
- COleCurrency() コンストラクト、 **COleCurrency** 0 (ゼロ) に初期化されるオブジェクト。  
  
- COleCurrency (`cySrc`) を構築、 **COleCurrency**オブジェクトから、[通貨](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)値。  
  
- COleCurrency (`curSrc`) を構築、 **COleCurrency** 、既存のオブジェクト**COleCurrency**オブジェクトです。 新しいオブジェクトは、ソース オブジェクトと同じ状態を持ちます。  
  
- COleCurrency (`varSrc`) を構築、 **COleCurrency**オブジェクトです。 変換しようと、 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)構造または`COleVariant`通貨型のオブジェクト ( `VT_CY`) 値です。 この変換が成功すると、新しいに変換後の値がコピー **COleCurrency**オブジェクトです。 値ではない場合、 **COleCurrency**オブジェクトがゼロ (0) と無効な状態に設定します。  
  
- `COleCurrency(`nUnits`, `nFractionalUnits') を構築、 **COleCurrency**指定した数値のコンポーネントからのオブジェクト。 小数部の絶対値が 10,000 を超える場合は、単位に、適切な調整が行われます。 部と小数部が符号付き long 値で指定されていることに注意してください。  
  
 詳細については、次を参照してください。、[通貨](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)と[VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)内のエントリ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次の例では、パラメーターの&0; と&2; つのパラメーターのコンス トラクターの影響を示します。  
  
 [!code-cpp[NVC_MFCOleContainer&#10;](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]  
  
##  <a name="format"></a>COleCurrency::Format  
 通貨値の書式設定された表現を作成するには、このメンバー関数を呼び出します。  
  
```  
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 ロケールの設定に対応するフラグを示します。 次のフラグだけでは、通貨に関連します。  
  
- **LOCALE_NOUSEROVERRIDE**カスタム ユーザー設定ではなく、システム既定ロケール設定を使用します。  
  
 `lcid`  
 変換に使用するロケール ID を示します。  
  
### <a name="return-value"></a>戻り値  
 A`CString`通貨の書式の値を格納します。  
  
### <a name="remarks"></a>コメント  
 ローカルの言語仕様 (ロケール Id) を使用して値が書式設定されます。 通貨記号は、返される値は含まれません。 場合はこの状態**COleCurrency**オブジェクトが null、戻り値は空の文字列です。 戻り値の文字列が文字列リソースで指定された状態が有効である場合は、 **IDS_INVALID_CURRENCY**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer&#11;](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]  
  
##  <a name="getstatus"></a>COleCurrency::GetStatus  
 状態 (有効) を取得するには、このメンバー関数を呼び出して、指定された**COleCurrency**オブジェクトです。  
  
```  
CurrencyStatus GetStatus() const;  
```  
  
### <a name="return-value"></a>戻り値  
 この状態が返されます**COleCurrency**値。  
  
### <a name="remarks"></a>コメント  
 戻り値は、`CurrencyStatus`列挙内で定義されている型、 **COleCurrency**クラスです。  
  
 `enum CurrencyStatus{`  
  
 `valid = 0,`  
  
 `invalid = 1,`  
  
 `null = 2,`  
  
 `};`  
  
 これらのステータス値の簡単な説明は、次の一覧を参照してください。  
  
- **COleCurrency::valid**ことを示しますがこの**COleCurrency**のオブジェクトが有効です。  
  
- **COleCurrency::invalid**ことを示しますがこの**COleCurrency**オブジェクトは無効です。 つまり、その値誤りがあります。  
  
- **COleCurrency::null**ことを示しますがこの**COleCurrency**オブジェクトが null では、このオブジェクトの値が指定されていないことです。 (これは、データベースの意味で「値を持たない、」C++ ではなく"null" **NULL**)。  
  
 状態、 **COleCurrency**オブジェクトが無効で、次の場合。  
  
-   値が設定されている場合、 **VARIANT**または`COleVariant`値を通貨値に変換できませんでした。  
  
-   このオブジェクトが、オーバーフローまたはアンダー フロー代入演算操作中、たとえば場合`+=`または** \* =**します。  
  
-   場合は、無効な値は、このオブジェクトに割り当てられました。  
  
-   このオブジェクトの状態が明示的に設定に使用して無効な[SetStatus](#setstatus)します。  
  
 操作についての詳細は、無効です。 次のメンバー関数を参照してください状態を設定することがあります。  
  
- [COleCurrency](#colecurrency)  
  
- [演算子 =](#operator_eq)  
  
- [演算子 + -](#operator_plus_minus)  
  
- [operator + =、=](#operator_plus_minus_eq)  
  
- [演算子 */](#operator_star)  
  
- [演算子 * =、/=](#operator_star_div_eq)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer&#12;](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]  
  
##  <a name="m_cur"></a>COleCurrency::m_cur  
 基になる[通貨](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)この構造体**COleCurrency**オブジェクトです。  
  
### <a name="remarks"></a>コメント  
  
> [!CAUTION]
>  値を変更、**通貨**構造体がこの関数によって返されるポインターではこの値を変更**COleCurrency**オブジェクトです。 このステータスは変更されません**COleCurrency**オブジェクトです。  
  
 詳細については、次を参照してください。、[通貨](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)内のエントリ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="m_status"></a>COleCurrency::m_status  
 このデータ メンバーの型は、列挙型`CurrencyStatus`、内で定義されている、 **COleCurrency**クラスです。  
  
```  
enum CurrencyStatus{  
    valid = 0,  
    invalid = 1,  
    null = 2,  
};  
```  
  
### <a name="remarks"></a>コメント  
 これらのステータス値の簡単な説明は、次の一覧を参照してください。  
  
- **COleCurrency::valid**ことを示しますがこの**COleCurrency**のオブジェクトが有効です。  
  
- **COleCurrency::invalid**ことを示しますがこの**COleCurrency**オブジェクトは無効です。 つまり、その値誤りがあります。  
  
- **COleCurrency::null**ことを示しますがこの**COleCurrency**オブジェクトが null では、このオブジェクトの値が指定されていないことです。 (これは、データベースの意味で「値を持たない、」C++ ではなく"null" **NULL**)。  
  
 状態、 **COleCurrency**オブジェクトが無効で、次の場合。  
  
-   値が設定されている場合、 **VARIANT**または`COleVariant`値を通貨値に変換できませんでした。  
  
-   このオブジェクトが、オーバーフローまたはアンダー フロー代入演算操作中、たとえば場合`+=`または** \* =**します。  
  
-   場合は、無効な値は、このオブジェクトに割り当てられました。  
  
-   このオブジェクトの状態が明示的に設定に使用して無効な[SetStatus](#setstatus)します。  
  
 操作についての詳細は、無効です。 次のメンバー関数を参照してください状態を設定することがあります。  
  
- [COleCurrency](#colecurrency)  
  
- [演算子 =](#operator_eq)  
  
- [演算子 +、-](#operator_plus_minus)  
  
- [演算子 + =、=](#operator_plus_minus_eq)  
  
- [演算子 */](#operator_star)  
  
- [演算子 * =、/、=](#operator_star_div_eq)  
  
    > [!CAUTION]
    >  このデータ メンバーは、高度なプログラミングに適しています。 インライン メンバー関数を使用する必要があります[GetStatus](#getstatus)と[SetStatus](#setstatus)します。 参照してください`SetStatus`このデータ メンバーを明示的に設定に関する注意事項についてさらには。  
  
##  <a name="operator_eq"></a>COleCurrency::operator =  
 これらのオーバー ロード代入演算子は、これを元の通貨値をコピー **COleCurrency**オブジェクトです。  
  
```  
const COleCurrency& operator=(CURRENCY cySrc);  
const COleCurrency& operator=(const COleCurrency& curSrc);  
  const COleCurrency& operator=(const VARIANT& varSrc);
```  
  
### <a name="remarks"></a>コメント  
 各演算子の簡単な説明に従います。  
  
- **演算子 = (** `cySrc` **)** 、`CURRENCY`に値をコピー、 **COleCurrency**オブジェクトとその状態は、有効な設定されています。  
  
- **演算子 = (** `curSrc` **)**値および状態の既存のオペランドの**COleCurrency**にこのオブジェクトがコピーされた**COleCurrency**オブジェクトです。  
  
- **演算子 = (** *varSrc* **)**場合の変換、`VARIANT`値 (または[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクト) の通貨 ( `VT_CY`) が成功すると、変換された値がコピーに**COleCurrency**オブジェクトとその状態は、有効な設定は、です。 変換が成功すると、ない場合の値、 **COleCurrency**オブジェクトの値が 0、その状態は無効にします。  
  
 詳細については、次を参照してください。、[通貨](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)と[VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)内のエントリ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer&#15;](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]  
  
##  <a name="operator_plus_minus"></a>COleCurrency::operator +、-  
 これらの演算子を使用して追加し、2 つ**COleCurrency**値やとの相互の符号を変更する、 **COleCurrency**値。  
  
```  
COleCurrency operator+(const COleCurrency& cur) const;  
COleCurrency operator-(const COleCurrency& cur) const;  
COleCurrency operator-() const;  
```  
  
### <a name="remarks"></a>コメント  
 結果の状態は null は、オペランドのいずれかのかどうかは**COleCurrency**値は null です。  
  
 かどうか算術演算のオーバーフローすると、その結果、 **COleCurrency**値が無効です。  
  
 オペランドが無効であり、もう一方の場合は、not null、結果のステータス**COleCurrency**値が無効です。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer&#16;](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]  
  
##  <a name="operator_plus_minus_eq"></a>COleCurrency::operator + =、=  
 加算し、減算することは、 **COleCurrency**値との間この**COleCurrency**オブジェクトです。  
  
```  
const COleCurrency& operator+=(const COleCurrency& cur);  
const COleCurrency& operator-=(const COleCurrency& cur);
```  
  
### <a name="remarks"></a>コメント  
 この状態は null オペランドのいずれかの場合**COleCurrency**オブジェクトが設定を null にします。  
  
 かどうか、算術演算がオーバーフローした、このステータス**COleCurrency**オブジェクトが設定されている無効にします。  
  
 オペランドのいずれかが無効で、もう一方が null でない場合のこの状態**COleCurrency**オブジェクトが設定されている無効にします。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer&17;](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]  
  
##  <a name="operator_star"></a>COleCurrency::operator *、/  
 拡大縮小することは、 **COleCurrency**の値を整数値。  
  
```  
COleCurrency operator*(long nOperand) const;  
COleCurrency operator/(long nOperand) const;  
```  
  
### <a name="remarks"></a>コメント  
 場合、 **COleCurrency**オペランドが null の場合、その結果のステータス**COleCurrency**値は null です。  
  
 算術演算がオーバーフローした場合、またはアンダー フロー、結果のステータス**COleCurrency**値が無効です。  
  
 場合、 **COleCurrency**オペランドが有効で、その結果のステータス**COleCurrency**値が無効です。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer&#18;](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]  
  
##  <a name="operator_star_div_eq"></a>COleCurrency::operator * =、/、=  
 スケール アップするのには、 **COleCurrency**の値を整数値。  
  
```  
const COleCurrency& operator*=(long nOperand);  
const COleCurrency& operator/=(long nOperand);
```  
  
### <a name="remarks"></a>コメント  
 場合、 **COleCurrency**オペランドが null の場合、このステータス**COleCurrency**オブジェクトが設定を null にします。  
  
 かどうか、算術演算がオーバーフローした、このステータス**COleCurrency**オブジェクトが設定されている無効にします。  
  
 場合、 **COleCurrency**オペランドが無効、この状態**COleCurrency**オブジェクトが設定されている無効にします。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer&#19;](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]  
  
##  <a name="operator_stream"></a>COleCurrency::operator &lt; &lt;、&gt;&gt;  
 診断をダンプし、アーカイブに格納することをサポートしています。  
  
```  
friend CDumpContext& operator<<(
    CDumpContext& dc,  
    COleCurrency curSrc);
 
friend CArchive& operator<<(
    CArchive& ar,  
    COleCurrency curSrc);
 
friend CArchive& operator>>(
    CArchive& ar,  
    COleCurrency& curSrc);
```  
  
### <a name="remarks"></a>コメント  
 抽出 ( ** >> **) 演算子は、アーカイブからの読み込みをサポートしています。  
  
##  <a name="operator_currency"></a>COleCurrency::operator 通貨  
 返します。、`CURRENCY`構造体の値がこれからコピー **COleCurrency**オブジェクトです。  
  
```  
operator CURRENCY() const; 
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="parsecurrency"></a>COleCurrency::ParseCurrency  
 通貨値を読み取るための文字列を解析するには、このメンバー関数を呼び出します。  
  
```  
BOOL ParseCurrency(
    LPCTSTR lpszCurrency,  
    DWORD dwFlags = 0,  
    LCID lcid = LANG_USER_DEFAULT);
 
throw(CMemoryException*); 
throw(COleException*);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszCurrency*  
 解析するには null で終わる文字列へのポインター。  
  
 `dwFlags`  
 ロケールの設定、フラグに対応するフラグを示します。  
  
- **LOCALE_NOUSEROVERRIDE**カスタム ユーザー設定ではなく、システム既定ロケール設定を使用します。  
  
 `lcid`  
 変換に使用するロケール ID を示します。  
  
### <a name="return-value"></a>戻り値  
 文字列が通貨値であり、それ以外の場合 0 を正常に変換された場合は 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 元の文字列内の数値以外の文字の意味のローカル言語仕様 (ロケール Id) を使用します。  
  
 ロケール ID の値の詳細については、次を参照してください。[複数の言語をサポートする](http://msdn.microsoft.com/en-us/47dc5add-232c-4268-b977-43e12da81ede)です。  
  
 文字列が通貨に正常に変換された場合の値、この値**COleCurrency**オブジェクトが有効な値とする状態に設定します。  
  
 文字列を通貨値に変換されませんでしたか、数値オーバーフローのこの状態が発生した場合**COleCurrency**オブジェクトが無効です。  
  
 この関数がスローするメモリ割り当てエラーのために文字列の変換が失敗した場合、[関数](../../mfc/reference/cmemoryexception-class.md)します。 この関数によってスローされる他のエラー状態、[関数](../../mfc/reference/coleexception-class.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer&#13;](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]  
  
##  <a name="colecurrency_relational_operators"></a>COleCurrency 関係演算子  
 2 つの通貨値を比較し、条件が true である場合は 0 以外を返しますそれ以外の場合 0 を返します。  
  
```  
BOOL operator==(const COleCurrency& cur) const;  
BOOL operator!=(const COleCurrency& cur) const;  
BOOL operator<(const COleCurrency& cur) const;  
BOOL operator>(const COleCurrency& cur) const;  
BOOL operator<=(const COleCurrency& cur) const;  
BOOL operator>=(const COleCurrency& cur) const;  
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  順序付けの操作の戻り値 ( ** < **、 ** \< = **、 ** > **、 ** >= **) は、オペランドのいずれかの状態が null または無効な場合、未定義です。 等値演算子 ( `==`、 `!=`) のオペランドの状態を検討してください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer&#20;](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]  
  
##  <a name="setcurrency"></a>COleCurrency::SetCurrency  
 単位とこれの小数部を設定するには、このメンバー関数を呼び出す**COleCurrency**オブジェクトです。  
  
```  
void SetCurrency(
    long nUnits,  
    long nFractionalUnits);
```  
  
### <a name="parameters"></a>パラメーター  
 `nUnits`, `nFractionalUnits`  
 これにコピーされる単位および小数部の部分 (1/10 で、000's) の値を示す**COleCurrency**オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 小数部の絶対値が 10,000 より大きい場合は、3 番目の例を次に示すように、単位に、適切な調整が行われます。  
  
 部と小数部が符号付き long 値で指定されていることに注意してください。 4 番目の次の例では、パラメーターの符号が異なる場合の処理を表示します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer&#14;](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]  
  
##  <a name="setstatus"></a>COleCurrency::SetStatus  
 このステータス (有効) に設定するには、このメンバー関数を呼び出す**COleCurrency**オブジェクトです。  
  
```  
void SetStatus(CurrencyStatus  status  );
```  
  
### <a name="parameters"></a>パラメーター  
 *status*  
 この新しいステータス**COleCurrency**オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 *ステータス*でパラメーターの値が定義されている、`CurrencyStatus`列挙型で、内で定義された、 **COleCurrency**クラスです。  
  
 `enum CurrencyStatus{`  
  
 `valid = 0,`  
  
 `invalid = 1,`  
  
 `null = 2,`  
  
 `};`  
  
 これらのステータス値の簡単な説明は、次の一覧を参照してください。  
  
- **COleCurrency::valid**ことを示しますがこの**COleCurrency**のオブジェクトが有効です。  
  
- **COleCurrency::invalid**ことを示しますがこの**COleCurrency**オブジェクトは無効です。 つまり、その値誤りがあります。  
  
- **COleCurrency::null**ことを示しますがこの**COleCurrency**オブジェクトが null では、このオブジェクトの値が指定されていないことです。 (これは、データベースの意味で「値を持たない、」C++ ではなく"null" **NULL**)。  
  
    > [!CAUTION]
    >  この関数は、高度なプログラミングに適しています。 この関数では、このオブジェクトのデータは変更されません。 Null または無効な状態に設定する最も使用されます。 注意してください、代入演算子 ([演算子 =](#operator_eq)) と[SetCurrency](#setcurrency)ソース値に基づいて、オブジェクトの状態を設定します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleVariant クラス](../../mfc/reference/colevariant-class.md)

