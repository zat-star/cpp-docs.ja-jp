---
title: "編集 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CRuntimeClass structure
- dynamic class information
- runtime, class information
- run-time class, CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
caps.latest.revision: 20
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
ms.openlocfilehash: 17994895aec5eee3fbe67bef5f80494988906df9
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cruntimeclass-structure"></a>編集
各クラスから派生した`CObject`に関連付けられている、`CRuntimeClass`構造を実行時にオブジェクトまたはその基底クラスに関する情報を取得に使用できます。  
  
## <a name="syntax"></a>構文  
  
```  
struct CRuntimeClass  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRuntimeClass::CreateObject](#createobject)|実行時に、オブジェクトを作成します。|  
|[で](#fromname)|実行時にわかりやすいクラス名を使用して、オブジェクトを作成します。|  
|[CRuntimeClass::IsDerivedFrom](#isderivedfrom)|クラスは、指定したクラスから派生されているかどうかを判断します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CRuntimeClass::m_lpszClassName](#m_lpszclassname)|クラスの名前。|  
|[CRuntimeClass::m_nObjectSize](#m_nobjectsize)|オブジェクトのサイズ (バイト単位)。|  
|[CRuntimeClass::m_pBaseClass](#m_pbaseclass)|ポインター、`CRuntimeClass`基本クラスの構造体。|  
|[CRuntimeClass::m_pfnCreateObject](#m_pfncreateobject)|オブジェクトを動的に作成する関数へのポインター。|  
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|返します。、 `CRuntimeClass` (時に動的に使用できるリンクを参照) のみを構成します。|  
|[CRuntimeClass::m_wSchema](#m_wschema)|クラスのスキーマの数。|  
  
## <a name="remarks"></a>コメント  
 `CRuntimeClass`構造体は、そのため、基本クラスはありません。  
  
 実行時にオブジェクトのクラスを判断することは、特別な型チェック関数の引数が必要なときに、またはオブジェクトのクラスに基づく特殊なコードの記述が必要に便利です。 ランタイム クラス情報は、C++ 言語によって直接サポートされていません。  
  
 `CRuntimeClass`ポインターなど、関連の C++ オブジェクトに関する情報を提供、`CRuntimeClass`の基本クラスと関連するクラスの ASCII クラス名。 この構造体は、既知の名前を使用して、関連するクラスは、特定のクラスから派生されているかどうかを指定することによってオブジェクトの種類を指定するオブジェクトを動的に作成するために使用できるさまざまな機能も実装します。  
  
 使用する方法について`CRuntimeClass`、記事を参照して[クラス情報にアクセスする](../../mfc/accessing-run-time-class-information.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CRuntimeClass`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="createobject"></a>CRuntimeClass::CreateObject  
 実行時に動的に指定したクラスを作成するには、この関数を呼び出します。  
  
```  
CObject* CreateObject();  
  
static CObject* PASCAL CreateObject(LPCSTR lpszClassName);  
  
static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszClassName`  
 作成するクラスの既知の名前。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたオブジェクトへのポインターまたは**NULL**クラス名が見つからなかったか、オブジェクトの作成に十分なメモリがある場合。  
  
### <a name="remarks"></a>コメント  
 派生したクラス`CObject`動的作成は、実行時に指定したクラスのオブジェクトを作成する機能をサポートできます。 ドキュメント、ビュー、およびフレーム クラスを動的に作成をたとえば、サポートする必要があります。 動的な作成の詳細については、 `CreateObject` 、メンバーを参照してください[CObject クラス](../../mfc/using-cobject.md)と[CObject クラス: 機能のレベルを指定する](../../mfc/specifying-levels-of-functionality.md)。  
  
### <a name="example"></a>例  
  例を参照してください[IsDerivedFrom](#isderivedfrom)します。  
  
##  <a name="fromname"></a>で  
 取得するには、この関数を呼び出して、`CRuntimeClass`既知の名前に関連付けられている構造体。  
  
```  
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);  
  
static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszClassName`  
 派生したクラスの既知の名前`CObject`します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CRuntimeClass`で渡されるときに、名前に対応するオブジェクト`lpszClassName`します。 この関数を返します**NULL**クラス名が検出されなかった場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample&17;](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]  
  
##  <a name="isderivedfrom"></a>CRuntimeClass::IsDerivedFrom  
 呼び出し元のクラスに指定されたクラスから派生されているかどうかを判断するには、この関数を呼び出して、*側*パラメーター。  
  
```  
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;

 
```  
  
### <a name="parameters"></a>パラメーター  
 *側*  
 派生したクラスの既知の名前`CObject`します。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合クラス通話`IsDerivedFrom`ベースから派生したクラスが`CRuntimeClass`構造体をパラメーターとして指定した以外の場合は、 **FALSE**します。  
  
### <a name="remarks"></a>コメント  
 リレーションシップは、「ウォーキング」チェーン派生クラスのメンバーのクラスから最上位までによって決定されます。 この関数はのみを返します**FALSE**基本クラスの一致が検出されない場合。  
  
> [!NOTE]
>  使用する、`CRuntimeClass`構造体を含める必要があります、 `IMPLEMENT_DYNAMIC`、 `IMPLEMENT_DYNCREATE`、または`IMPLEMENT_SERIAL`マクロでは、実行時のオブジェクトの情報を取得するクラスの実装です。  
  
 使用する方法について`CRuntimeClass`、記事を参照して[CObject クラス: クラス情報にアクセスする](../../mfc/accessing-run-time-class-information.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample&#18;](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]  
  
##  <a name="m_lpszclassname"></a>CRuntimeClass::m_lpszClassName  
 ASCII クラス名を含む null で終わる文字列。  
  
### <a name="remarks"></a>コメント  
 この名前を使用してクラスのインスタンスを作成するために使用できます、`FromName`メンバー関数。  
  
### <a name="example"></a>例  
  例を参照してください[IsDerivedFrom](#isderivedfrom)します。  
  
##  <a name="m_nobjectsize"></a>CRuntimeClass::m_nObjectSize  
 バイト単位でのオブジェクトのサイズ。  
  
### <a name="remarks"></a>コメント  
 オブジェクトは、割り当てられたメモリを指すデータ メンバーを持っている場合はそのメモリのサイズは含まれません。  
  
### <a name="example"></a>例  
  例を参照してください[IsDerivedFrom](#isderivedfrom)します。  
  
##  <a name="m_pbaseclass"></a>CRuntimeClass::m_pBaseClass  
 このデータ メンバーがへのポインターを含む場合は、アプリケーションは、MFC と静的にリンク、`CRuntimeClass`基本クラスの構造体。  
  
### <a name="remarks"></a>コメント  
 アプリケーションは、MFC ライブラリに動的にリンクすることが場合、は、次を参照してください。 [m_pfnGetBaseClass](#m_pfngetbaseclass)します。  
  
### <a name="example"></a>例  
  例を参照してください[IsDerivedFrom](#isderivedfrom)します。  
  
##  <a name="m_pfncreateobject"></a>CRuntimeClass::m_pfnCreateObject  
 クラスのオブジェクトを作成する既定のコンス トラクターへの関数ポインター。  
  
### <a name="remarks"></a>コメント  
 このポインターは有効なは、クラスには、動的な作成がサポートされている場合のみそれ以外の場合、関数が返す**NULL**します。  
  
##  <a name="m_pfngetbaseclass"></a>CRuntimeClass::m_pfnGetBaseClass  
 アプリケーションは、共有 DLL としての MFC ライブラリを使用する場合は、データへのポインターを返す関数、`CRuntimeClass`基本クラスの構造体。  
  
### <a name="remarks"></a>コメント  
 アプリケーションは、MFC ライブラリに静的にリンクすることが場合、は、次を参照してください。 [m_pBaseClass](#m_pbaseclass)します。  
  
### <a name="example"></a>例  
  例を参照してください[IsDerivedFrom](#isderivedfrom)します。  
  
##  <a name="m_wschema"></a>CRuntimeClass::m_wSchema  
 スキーマの数 (シリアル化できないクラスの場合は-1)。  
  
### <a name="remarks"></a>コメント  
 スキーマ番号の詳細については、次を参照してください。、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロです。  
  
### <a name="example"></a>例  
  例を参照してください[IsDerivedFrom](#isderivedfrom)します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CObject::GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)   
 [使うため](../../mfc/reference/cobject-class.md#iskindof)   
 [対象となります。](run-time-object-model-services.md#runtime_class)   
 [新規クラス](run-time-object-model-services.md#implement_dynamic)   
 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)   
 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)




