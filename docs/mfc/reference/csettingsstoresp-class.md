---
title: "CSettingsStoreSP クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSettingsStoreSP
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStoreSP class
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
caps.latest.revision: 18
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 00131a3c03fdb2c1c1de247a8e1bdcfd9beaf852
ms.lasthandoff: 02/24/2017

---
# <a name="csettingsstoresp-class"></a>CSettingsStoreSP クラス
`CSettingsStoreSP`クラスのインスタンスの作成に使用できるヘルパー クラスであり、 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSettingsStoreSP  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|`CSettingsStoreSP` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSettingsStoreSP::Create](#create)|派生したクラスのインスタンスを作成`CSettingsStore`します。|  
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|ランタイム クラスを設定します。 `Create`メソッドはランタイム クラスを使用して作成するオブジェクトのクラスを決定します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|`m_dwUserData`|カスタム ユーザー データに格納されている、`CSettingsStoreSP`オブジェクトです。 コンス トラクターでは、このデータを指定する、`CSettingsStoreSP`オブジェクトです。|  
|`m_pRegistry`|`CSettingsStore`-派生オブジェクトを`Create`メソッドを作成します。|  
  
## <a name="remarks"></a>コメント  
 使用することができます、 `CSettingsStoreSP` MFC レジストリのすべての操作を XML ファイルやデータベースなど、他の場所にリダイレクトするクラス。 その場合は、次の手順を実行します。  
  
1.  クラスの作成 (よう`CMyStore`) から派生`CSettingsStore`します。  
  
2.  使用[DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)と[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)マクロは、カスタムで`CSettingsStore`を動的に作成を有効にするクラス。  
  
3.  仮想関数をオーバーライドし、実装、`Read`と`Write`カスタム クラス内の関数です。 任意の場所にデータを読み書きするには、他の機能を実装します。  
  
4.  アプリケーションで呼び出す`CSettingsStoreSP::SetRuntimeClass`へのポインターを渡すと、[編集](../../mfc/reference/cruntimeclass-structure.md)クラスから取得します。  
  
 フレームワークは通常、レジストリにアクセス、ときに今すぐ動的に、カスタム クラスをインスタンス化され読み取りまたは書き込みのデータを使用します。  
  
 `CSettingsStoreSP::SetRuntimeClass`グローバルな静的変数を使用します。 したがって、1 つだけのカスタム ストアは、時に使用します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxsettingsstore.h  
  
##  <a name="a-namecreatea--csettingsstorespcreate"></a><a name="create"></a>CSettingsStoreSP::Create  
 派生したオブジェクトの新しいインスタンスを作成、 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)します。  
  
```  
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bAdmin`  
 決定するブール値パラメーターかどうか、`CSettingsStore`管理者モードでオブジェクトを作成します。  
  
 [入力] `bReadOnly`  
 決定するブール値パラメーターかどうか、`CSettingsStore`読み取り専用アクセスにオブジェクトを作成します。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたへの参照を`CSettingsStore`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 メソッドを使用する[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)オブジェクトの種類を決定する`CSettingsStoreSP::Create`が作成されます。 既定では、このメソッドを作成、`CSettingsStore`オブジェクトです。  
  
 作成する場合、`CSettingsStore`管理者モードでオブジェクトのすべてのレジストリへのアクセスの既定の場所は、HKEY_LOCAL_MACHINE です。 それ以外の場合、すべてのレジストリへのアクセスの既定の場所は、HKEY_CURRENT_USER です。  
  
 場合`bAdmin`は`TRUE`アプリケーションの管理権限が必要です。 それ以外の場合、レジストリのアクセスを試行するときに失敗になります。  
  
### <a name="example"></a>例  
 次の例では、使用して、`Create`のメソッド、`CSettingsStoreSP`クラスです。  
  
 [!code-cpp[NVC_MFC_RibbonApp #&33;](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]  
  
##  <a name="a-namecsettingsstorespa--csettingsstorespcsettingsstoresp"></a><a name="csettingsstoresp"></a>CSettingsStoreSP::CSettingsStoreSP  
 構築、 [CSettingsStoreSP クラス](../../mfc/reference/csettingsstoresp-class.md)オブジェクトです。  
  
```  
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwUserData`  
 ユーザー定義データを`CSettingsStoreSP`オブジェクト ストアです。  
  
### <a name="remarks"></a>コメント  
 `CSettingsStoreSP`オブジェクトからデータを格納する`dwUserData`プロテクト メンバー変数に`m_dwUserData`します。  
  
##  <a name="a-namesetruntimeclassa--csettingsstorespsetruntimeclass"></a><a name="setruntimeclass"></a>CSettingsStoreSP::SetRuntimeClass  
 ランタイム クラスを設定します。 メソッド[CSettingsStoreSP::Create](#create)ランタイム クラスを使用して作成するオブジェクトの種類を決定します。  
  
```  
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pRTI`  
 派生したクラスのランタイム クラス情報へのポインター、 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`成功した場合`FALSE`場合は、クラスがで識別される`pRTI`から派生していない`CSettingsStore`します。  
  
### <a name="remarks"></a>コメント  
 使用することができます、 [CSettingsStoreSP クラス](../../mfc/reference/csettingsstoresp-class.md)からクラスを派生させる`CSettingsStore`します。 メソッドを使用して`SetRuntimeClass`から派生したカスタム クラスのオブジェクトを作成する`CSettingsStore`です。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)

