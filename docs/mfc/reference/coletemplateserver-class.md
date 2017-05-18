---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleTemplateServer
- AFXDISP/COleTemplateServer
- AFXDISP/COleTemplateServer::COleTemplateServer
- AFXDISP/COleTemplateServer::ConnectTemplate
- AFXDISP/COleTemplateServer::Unregister
- AFXDISP/COleTemplateServer::UpdateRegistry
dev_langs:
- C++
helpviewer_keywords:
- Automation servers [C++], implementing
- servers, OLE
- OLE server applications, managing server documents
- link containers [C++]
- visual editing, servers
- OLE link containers
- COleTemplateServer class
- OLE server applications, COleTemplateServer class
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ea82939cd0e8a8ba5612c65d238be8ae9996ef08
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="coletemplateserver-class"></a>関数のクラス
OLE のビジュアル編集サーバー、オートメーション サーバー、およびリンク コンテナー (埋め込みアイテムへのリンクをサポートするアプリケーションのことです) で使います。  
  
## <a name="syntax"></a>構文  
  
```  
class COleTemplateServer : public COleObjectFactory  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleTemplateServer::COleTemplateServer](#coletemplateserver)|`COleTemplateServer` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleTemplateServer::ConnectTemplate](#connecttemplate)|ドキュメント テンプレートを基になる接続`COleObjectFactory`オブジェクトです。|  
|[COleTemplateServer::Unregister](#unregister)|関連付けられたドキュメント テンプレートの登録を解除します。|  
|[COleTemplateServer::UpdateRegistry](#updateregistry)|ドキュメント型を OLE システム レジストリに登録します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、クラスから派生[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); 通常、使用する`COleTemplateServer`独自のクラスを派生するのではなく、直接します。 `COleTemplateServer`使用して、 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) server ドキュメントを管理するオブジェクト。 使用`COleTemplateServer`フル サーバー、つまりスタンドアロン アプリケーションとして実行できるサーバーを実装する場合。 完全一般サーバーは、マルチ ドキュメント インターフェイス (MDI) アプリケーションでは、シングル ドキュメント インターフェイス (SDI) アプリケーションがサポートされています。 1 つ`COleTemplateServer`アプリケーションがサポートするサーバーのドキュメントの種類ごとに必要なオブジェクトです。 つまり、場合は、サーバー アプリケーションでは、ワークシートとグラフの両方をサポートする必要がありますが&2; つ`COleTemplateServer`オブジェクトです。  
  
 `COleTemplateServer`上書き、`OnCreateInstance`によって定義されたメンバー関数`COleObjectFactory`します。 このメンバー関数は、適切な型の C++ オブジェクトを作成するためにフレームワークによって呼び出されます。  
  
 サーバーの詳細については、記事を参照してください。[サーバー: サーバーを実装する](../../mfc/servers-implementing-a-server.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)  
  
 `COleTemplateServer`  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="coletemplateserver"></a>COleTemplateServer::COleTemplateServer  
 `COleTemplateServer` オブジェクトを構築します。  
  
```  
COleTemplateServer();
```  
  
### <a name="remarks"></a>コメント  
 使用した簡単な説明、`COleTemplateServer`を参照してください、[直接](../../mfc/reference/colelinkingdoc-class.md)クラスの概要です。  
  
##  <a name="connecttemplate"></a>COleTemplateServer::ConnectTemplate  
 指すドキュメント テンプレートを接続する`pDocTemplate`、基になる[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)オブジェクトです。  
  
```  
void ConnectTemplate(
    REFCLSID clsid,  
    CDocTemplate* pDocTemplate,  
    BOOL bMultiInstance);
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 テンプレートを要求する OLE クラス ID への参照。  
  
 `pDocTemplate`  
 ドキュメント テンプレートへのポインター。  
  
 `bMultiInstance`  
 アプリケーションの&1; つのインスタンスが複数のインスタンス化をサポートできるかどうかを示します。 場合**TRUE**オブジェクトを作成する要求ごとに、アプリケーションの複数のインスタンスを起動します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [CLSID キー](http://msdn.microsoft.com/library/windows/desktop/ms691424)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="unregister"></a>COleTemplateServer::Unregister  
 関連付けられたドキュメント テンプレートの登録を解除します。  
  
```  
BOOL Unregister();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は TRUE、それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 EnterRemarks  
  
##  <a name="updateregistry"></a>COleTemplateServer::UpdateRegistry  
 ドキュメント テンプレート文字列からファイルの種類の情報を読み込んで OLE システム レジストリに格納します。  
  
```  
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL,  
    BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nAppType`  
 値、 **OLE_APPTYPE**列挙体、列挙子。H. 次の値のいずれかを取ります。  
  
- `OAT_INPLACE_SERVER`サーバーは、サーバー全体のユーザー インターフェイスを持っています。  
  
- `OAT_SERVER`サーバーは、埋め込みだけをサポートします。  
  
- `OAT_CONTAINER`コンテナーは、埋め込みオブジェクトへのリンクをサポートします。  
  
- `OAT_DISPATCH_OBJECT`オブジェクトが`IDispatch`に対応します。  
  
- **OAT_DOC_OBJECT_SERVER**両方をサポートするサーバーの埋め込みとドキュメント オブジェクト コンポーネント モデルです。  
  
 `rglpszRegister`  
 エントリが存在しない場合にのみ、レジストリに書き込まれるエントリの一覧です。  
  
 `rglpszOverwrite`  
 既にエントリが存在するかどうかに関係なく、レジストリに書き込まれるエントリの一覧です。  
  
 `bRegister`  
 クラスを登録するかどうかを決定します。 場合`bRegister`は**TRUE**クラスが、システム レジストリに登録されています。 それ以外の場合、クラスが登録解除します。  
  
### <a name="remarks"></a>コメント  
 呼び出して、登録情報が読み込まれる[CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)します。 取得した部分文字列は、インデックスによって識別される**取り出さ**、 **regFileTypeName**、および**fileNewName**」を参照して、`GetDocString`ページを参照します。  
  
 場合、**取り出さ**部分文字列が空またはへの呼び出し`GetDocString`何らかの理由でこの関数が失敗したが失敗し、レジストリ、ファイルの情報が入力されていません。  
  
 引数の情報は、`rglpszRegister`と`rglpszOverwrite`を呼び出すことによって、レジストリに書き込まれる[AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass)します。 既定の情報が登録されているは、2 つの引数が**NULL**、ほとんどのアプリケーションに適しています。 これらの引数の情報の構造については、次を参照してください。`AfxOleRegisterServerClass`します。  
  
 詳細については、次を参照してください。 [IDispatch インターフェイスを実装する](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [COleObjectFactory クラス](../../mfc/reference/coleobjectfactory-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)   
 [実際のクラス](../../mfc/reference/coleserveritem-class.md)

