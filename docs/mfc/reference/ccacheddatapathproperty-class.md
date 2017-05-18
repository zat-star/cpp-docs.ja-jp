---
title: "プロパティ クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], asynchronous
- CCachedDataPathProperty class
- OLE controls [C++], asynchronous
- asynchronous controls [C++]
- memory files [C++]
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6e3f54e6429456be24cbe18471abd1705bbe0034
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccacheddatapathproperty-class"></a>プロパティ クラス
非同期で転送し、メモリ ファイルにキャッシュする OLE コントロール プロパティを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CCachedDataPathProperty : public CDataPathProperty  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|`CCachedDataPathProperty` オブジェクトを構築します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile`データをキャッシュするオブジェクト。|  
  
## <a name="remarks"></a>コメント  
 メモリ ファイルでは、ディスクではなく、RAM 内に格納され、一時的な高速の転送に適しています。  
  
 と共に**CAysncMonikerFile**と`CDataPathProperty`、 `CCachedDataPathProperty` OLE コントロールで非同期モニカーを使用するための機能を提供します。 `CCachedDataPathProperty`オブジェクトの場合、URL またはファイルのソースからデータを非同期的に転送を使用して、メモリ ファイルに格納できる、`m_Cache`パブリック変数です。 メモリ ファイル内のすべてのデータが格納されているし、オーバーライドする必要はありません[OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)通知を監視し、応答するのでない限りです。 たとえば、次のように、大規模なを転送する場合。GIF ファイルおよび自体が再描画するより多くのデータが到着したコントロールに通知するオーバーライド`OnDataAvailable`通知します。  
  
 クラス`CCachedDataPathProperty`から派生した`CDataPathProperty`します。  
  
 インターネット アプリケーションで非同期モニカーと ActiveX コントロールを使用する方法の詳細については、次のトピックを参照してください。  
  
- [インターネット最初のステップ: ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)  
  
- [インターネット最初のステップ: 非同期モニカー](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [関数](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 [関数](../../mfc/reference/cdatapathproperty-class.md)  
  
 `CCachedDataPathProperty`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h  
  
##  <a name="ccacheddatapathproperty"></a>CCachedDataPathProperty::CCachedDataPathProperty  
 `CCachedDataPathProperty` オブジェクトを構築します。  
  
```  
CCachedDataPathProperty(COleControl* pControl = NULL);

 
CCachedDataPathProperty(
    LPCTSTR lpszPath,  
    COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pControl`  
 これに関連する ActiveX コントロール オブジェクトへのポインター`CCachedDataPathProperty`オブジェクトです。  
  
 `lpszPath`  
 可能性のある絶対または相対パス、パスは、プロパティの実際の絶対位置を参照する非同期モニカーの作成に使用します。 `CCachedDataPathProperty`Url はファイル名を使用します。 場合は、`CCachedDataPathProperty`ファイルのオブジェクト、パスに file:// 先頭に追加します。  
  
### <a name="remarks"></a>コメント  
 `COleControl`によって指されるオブジェクト`pControl`によって使用される[開く](../../mfc/reference/cdatapathproperty-class.md#open)派生クラスによって取得します。 場合`pControl`は**NULL**で使用されるコントロール**開く**で設定する必要があります[SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol)します。 場合`lpszPath`は**NULL**を使用してパスを渡すことができます**開く**を設定または[SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath)します。  
  
##  <a name="m_cache"></a>CCachedDataPathProperty::m_Cache  
 データがキャッシュされる、メモリ ファイルのクラス名が含まれています。  
  
```  
CMemFile m_Cache;  
```  
  
### <a name="remarks"></a>コメント  
 メモリ ファイルは、ディスクではなく RAM に格納されます。  
  
## <a name="see-also"></a>関連項目  
 [関数のクラス](../../mfc/reference/cdatapathproperty-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/cdatapathproperty-class.md)

