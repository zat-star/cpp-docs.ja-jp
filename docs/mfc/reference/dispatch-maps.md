---
title: "ディスパッチ マップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- dispatch maps. macros
- dispatch maps
- dispatch map macros
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
caps.latest.revision: 14
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 48e5d1fe207089733caa5ed9e8ca30c2de21f95f
ms.lasthandoff: 02/24/2017

---
# <a name="dispatch-maps"></a>ディスパッチ マップ
OLE オートメーションでは、メソッドを呼び出すと、アプリケーション間でプロパティにアクセスする方法を提供します。 これらの要求をディスパッチするためには、Microsoft Foundation Class ライブラリによって提供されるメカニズムは、「ディスパッチ マップ」のオブジェクトの関数とプロパティだけでなく、データ型および関数の引数のプロパティ自体の内部および外部の名前を指定します。  
  
### <a name="dispatch-maps"></a>ディスパッチ マップ  
  
|||  
|-|-|  
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|クラスのメソッドとプロパティ (クラス宣言で使用する必要があります) を公開するディスパッチ マップを使用することを宣言します。|  
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|ディスパッチ マップの定義を開始します。|  
|[END_DISPATCH_MAP](#end_dispatch_map)|ディスパッチ マップの定義を終了します。|  
|[DISP_FUNCTION](#disp_function)|ディスパッチ マップで使用すると、OLE オートメーション関数を定義します。|  
|[DISP_PROPERTY](#disp_property)|OLE オートメーションのプロパティを定義します。|  
|[DISP_PROPERTY_EX](#disp_property_ex)|OLE オートメーションのプロパティを定義し、Get と Set 関数の名前します。|  
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|通知の使用の OLE オートメーション プロパティを定義します。|  
|[DISP_PROPERTY_PARAM](#disp_property_param)|Get と Set 関数のパラメーターと名前を受け取るための OLE オートメーション プロパティを定義します。|  
|[DISP_DEFVALUE](#disp_defvalue)|既存のプロパティ オブジェクトの既定値を使用できます。|  
  
##  <a name="a-namedeclaredispatchmapa--declaredispatchmap"></a><a name="declare_dispatch_map"></a>DECLARE_DISPATCH_MAP  
 場合、 `CCmdTarget`-プログラム内の派生クラスは、クラスがそのメソッドとプロパティを公開するディスパッチ マップを提供する必要がありますの OLE オートメーションをサポートしています。  
  
```   
DECLARE_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>コメント  
 使用して、`DECLARE_DISPATCH_MAP`クラス宣言の末尾のマクロです。 次に、します。クラスのメンバーを定義する CPP ファイルの機能を使用して、`BEGIN_DISPATCH_MAP`マクロです。 クラスが公開メソッドとプロパティのマクロのエントリを含める ( `DISP_FUNCTION`、`DISP_PROPERTY`など)。 最後に、使用して、`END_DISPATCH_MAP`マクロです。  
  
> [!NOTE]
>  後のすべてのメンバーを宣言する場合`DECLARE_DISPATCH_MAP`、新しいアクセスの種類を指定する必要があります (**パブリック**、 `private`、または`protected`) にします。  
  
 アプリケーション ウィザードとコードのウィザードでは、オートメーション クラスの作成とディスパッチ マップの管理を支援します。 ディスパッチ マップの詳細については、次を参照してください。[オートメーション サーバー](../../mfc/automation-servers.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAutomation&#10;](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  

##  <a name="a-namebegindispatchmapa--begindispatchmap"></a><a name="begin_dispatch_map"></a>BEGIN_DISPATCH_MAP  
 ディスパッチ マップの定義を宣言します。  
  
```  
BEGIN_DISPATCH_MAP(theClass, baseClass)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 このディスパッチ マップを所有しているクラスの名前を指定します。  
  
 `baseClass`  
 基本クラスの名前を指定`theClass`します。  
  
### <a name="remarks"></a>コメント  
 クラスのメンバー関数を定義する実装 (.cpp) ファイル、ディスパッチ マップを開始、`BEGIN_DISPATCH_MAP`マクロは、それぞれのディスパッチ関数と、プロパティのマクロのエントリを追加ししでディスパッチ マップ、`END_DISPATCH_MAP`マクロです。  

### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  

##  <a name="a-nameenddispatchmapa--enddispatchmap"></a><a name="end_dispatch_map"></a>END_DISPATCH_MAP  
 ディスパッチ マップの定義を終了します。  
  
```   
END_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>コメント  
 組み合わせて使用する必要があります`BEGIN_DISPATCH_MAP`します。  

### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  

##  <a name="a-namedispfunctiona--dispfunction"></a><a name="disp_function"></a>DISP_FUNCTION  
 ディスパッチ マップでは、OLE オートメーション関数を定義します。  
  
```   
DISP_FUNCTION(
  theClass, 
  pszName, 
  pfnMember, 
  vtRetVal, 
  vtsParams)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 クラスの名前です。  
  
 `pszName`  
 関数の外部名。  
  
 `pfnMember`  
 メンバー関数の名前。  
  
 `vtRetVal`  
 関数の戻り値の型を指定する値。  
  
 `vtsParams`  
 スペースで区切られた一連の関数のパラメーター リストを指定する&1; つ以上の定数です。  
  
### <a name="remarks"></a>コメント  
 `vtRetVal`型の引数は、 **VARTYPE**します。 この引数に次の考えられる値から取得されます、`VARENUM`列挙体。  
  
|シンボル|戻り値の型|  
|------------|-----------------|  
|`VT_EMPTY`|`void`|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**日付**|  
|`VT_BSTR`|`BSTR`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**バリアント**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 `vtsParams`引数がスペースで区切られた一連の値から、 **vts _**定数です。 1 つ以上のスペース (コンマではなく) で区切られたこれらの値は、関数のパラメーター リストを指定します。 次に例を示します。 
  
 [!code-cpp[NVC_MFCAutomation&#14;](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]  
  
 短整数へのポインターの後に短整数を含むリストを指定します。  
  
 **Vts _**定数とその意味は次のようには。  
  
|シンボル|パラメーターの型|  
|------------|--------------------|  
|**VTS_I2**|`Short`|  
|**VTS_I4**|`Long`|  
|**VTS_R4**|**浮動小数点数**|  
|**VTS_R8**|`Double`|  
|**VTS_CY**|**const CY**または**CY\***|  
|**VTS_DATE**|**日付**|  
|**VTS_BSTR**|`LPCSTR`|  
|**VTS_DISPATCH**|`LPDISPATCH`|  
|**VTS_SCODE**|`SCODE`|  
|**VTS_BOOL**|**BOOL**|  
|**VTS_VARIANT**|**const バリアント\***または**VARIANT >/documents/report1.rdl」の**|  
|**VTS_UNKNOWN**|`LPUNKNOWN`|  
|**VTS_PI2**|**短い\***|  
|**VTS_PI4**|**長い\***|  
|**VTS_PR4**|**浮動小数点数\***|  
|**VTS_PR8**|**二重\***|  
|**VTS_PCY**|**CY\***|  
|**VTS_PDATE**|**日付\***|  
|**VTS_PBSTR**|**BSTR\***|  
|**VTS_PDISPATCH**|**LPDISPATCH\***|  
|**VTS_PSCODE**|**SCODE\***|  
|**VTS_PBOOL**|**BOOL\***|  
|**VTS_PVARIANT**|**バリアント\***|  
|**VTS_PUNKNOWN**|**LPUNKNOWN\***|  
|**VTS_NONE**|パラメーターなし|  

### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h 

##  <a name="a-namedisppropertya--dispproperty"></a><a name="disp_property"></a>DISP_PROPERTY  
 ディスパッチ マップ内の OLE オートメーション プロパティを定義します。  
  
```   
DISP_PROPERTY(
  theClass, 
  pszName, 
  memberName, 
  vtPropType)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 クラスの名前です。  
  
 `pszName`  
 プロパティの外部名。  
  
 `memberName`  
 プロパティが格納されているメンバー変数の名前。  
  
 `vtPropType`  
 プロパティの型を指定する値。  
  
### <a name="remarks"></a>コメント  
 `vtPropType`型の引数は、 **VARTYPE**します。 この引数に指定できる値はから取得、`VARENUM`列挙体。  
  
|シンボル|**プロパティの型**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**日付**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**バリアント**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 外部クライアントにプロパティで指定されたメンバー変数の値が変更されたとき`memberName`; を変更、変更の通知はありません。  

### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h 

##  <a name="a-namedisppropertyexa--disppropertyex"></a><a name="disp_property_ex"></a>DISP_PROPERTY_EX  
 OLE オートメーションのプロパティと名前を取得およびディスパッチ マップ内のプロパティの値を設定するための関数を定義します。  
  
```   
DISP_PROPERTY_EX(
  theClass, 
  pszName, 
  memberGet, 
  memberSet, 
  vtPropType)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 クラスの名前です。  
  
 `pszName`  
 プロパティの外部名。  
  
 `memberGet`  
 プロパティを取得するために使用するメンバー関数の名前。  
  
 `memberSet`  
 プロパティの設定を使用するメンバー関数の名前です。  
  
 `vtPropType`  
 プロパティの型を指定する値。  
  
### <a name="remarks"></a>コメント  
 `memberGet`と`memberSet`関数がによって決定されるシグネチャを持つ、`vtPropType`引数。 `memberGet`関数は引数を使用しないで指定された型の値を返します`vtPropType`します。 `memberSet`関数は、指定された型の引数を受け取る`vtPropType`何も返しません。  
  
 `vtPropType`型の引数は、 **VARTYPE**します。 この引数に指定できる値はから取得、`VARENUM`列挙します。 これらの値の一覧は、「解説」を参照してください、`vtRetVal`パラメーター [DISP_FUNCTION](#disp_function)します。 `VT_EMPTY`で挙げられて、 `DISP_FUNCTION` remarks、プロパティのデータ型としては許可されません。  

### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h 

##  <a name="a-namedisppropertynotifya--disppropertynotify"></a><a name="disp_property_notify"></a>DISP_PROPERTY_NOTIFY  
 ディスパッチ マップ内には、通知付きの OLE オートメーション プロパティを定義します。  
  
```   
DISP_PROPERTY_NOTIFY(
  theClass, 
  szExternalName, 
  memberName, 
  pfnAfterSet, 
  vtPropType)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 クラスの名前です。  
  
 `szExternalName`  
 プロパティの外部名。  
  
 `memberName`  
 プロパティが格納されているメンバー変数の名前。  
  
 `pfnAfterSet`  
 通知関数の名前`szExternalName`します。  
  
 `vtPropType`  
 プロパティの型を指定する値。  
  
### <a name="remarks"></a>コメント  
 定義されたプロパティとは異なり`DISP_PROPERTY`で定義されているプロパティ`DISP_PROPERTY_NOTIFY`で指定された関数が自動的に呼び出さ`pfnAfterSet`プロパティが変更されたとき。  
  
 `vtPropType`型の引数は、 **VARTYPE**します。 この引数に指定できる値はから取得、`VARENUM`列挙体。  
  
|シンボル|**プロパティの型**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**日付**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**バリアント**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  

### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h 

##  <a name="a-namedisppropertyparama--disppropertyparam"></a><a name="disp_property_param"></a>DISP_PROPERTY_PARAM  
 個別にアクセスされるプロパティを定義**取得**と`Set`メンバー関数。  
  
```   
DISP_PROPERTY_PARAM(
  theClass, 
  pszExternalName, 
  pfnGet, 
  pfnSet, 
  vtPropType,
  vtsParams)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 クラスの名前です。  
  
 *pszExternalName*  
 プロパティの外部名。  
  
 `pfnGet`  
 プロパティを取得するために使用するメンバー関数の名前。  
  
 `pfnSet`  
 プロパティの設定を使用するメンバー関数の名前です。  
  
 `vtPropType`  
 プロパティの型を指定する値。  
  
 `vtsParams`  
 スペースで区切られた文字列**vts _**のバリアント型パラメーターが型パラメーターごとに&1; つです。  
  
### <a name="remarks"></a>コメント  
 異なり、`DISP_PROPERTY_EX`マクロ、このマクロを使用すると、プロパティのパラメーター リストを指定します。 これは、インデックスを作成またはパラメーター化されているプロパティを実装するのに便利です。  
  
### <a name="example"></a>例  
 Get の次の宣言を検討し、メンバーのプロパティにアクセスする際に、特定の行と列を要求するユーザーをできるようにする関数を設定します。  
  
 [!code-cpp[NVC_MFCActiveXControl&#9;](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]  
  
 これらは、次に対応して`DISP_PROPERTY_PARAM`コントロールのディスパッチ マップ マクロ。  
  
 [!code-cpp[NVC_MFCActiveXControl&#10;](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]  
  
 別の例としては、次の取得を検討してくださいし、set メンバー関数。  
  
 [!code-cpp[NVC_MFCActiveXControl&#11;](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]  
  
 これらは、次に対応して`DISP_PROPERTY_PARAM`コントロールのディスパッチ マップ マクロ。  
  
 [!code-cpp[NVC_MFCActiveXControl&#12;](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h 

##  <a name="a-namedispdefvaluea--dispdefvalue"></a><a name="disp_defvalue"></a>DISP_DEFVALUE  
 既存のプロパティ オブジェクトの既定値を使用できます。  
  
```   
DISP_DEFVALUE(theClass, pszName)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 クラスの名前です。  
  
 `pszName`  
 オブジェクトの"value"を表すプロパティの外部名。  
  
### <a name="remarks"></a>コメント  
 既定値を使用するには、Visual Basic アプリケーションの簡単なオートメーション オブジェクトのプログラミングすることができます。  
  
 オブジェクトの「既定値」は、プロパティが取得または設定オブジェクトへの参照は、プロパティまたはメンバー関数を指定していない場合ですです。  

### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h 

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

