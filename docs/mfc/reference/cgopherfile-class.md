---
title: "CGopherFile クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
dev_langs:
- C++
helpviewer_keywords:
- gopher protocol files
- Internet, gopher
- CGopherFile class
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 40c1e385d0f58095c2aa79cc23168fc00f48ed9b
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherfile-class"></a>CGopherFile クラス
gopher サーバー上のファイルを検索し、読み込む機能が用意されています。  
  
> [!NOTE]
>  クラスは、 `CGopherConnection`、 `CGopherFile`、 `CGopherFileFind`、`CGopherLocator`し、Windows XP のプラットフォームで機能しませんが、以前のプラットフォームで動作し続けますので、そのメンバーは廃止されました。  
  
## <a name="syntax"></a>構文  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CGopherFile::CGopherFile](#cgopherfile)|`CGopherFile` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 Gopher サービスには、ユーザーが情報を検索するためのメニュー方式のインターフェイスとして主にこのサービスが動作するために、gopher ファイルにデータを書き込むことはできません。 `CGopherFile`メンバー関数**書き込み**、 `WriteString`、および`Flush`は適用されていない`CGopherFile`します。 これらの関数を呼び出すこと、`CGopherFile`オブジェクトを返す、[行わない](../../mfc/reference/cnotsupportedexception-class.md)します。  
  
 方法について説明する`CGopherFile`他のインターネットの MFC クラスと動作は、記事を参照して[WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="cgopherfile"></a>CGopherFile::CGopherFile  
 このメンバー関数が作成すると呼ばれる、`CGopherFile`オブジェクトです。  
  
```  
CGopherFile(
    HINTERNET hFile,  
    CGopherLocator& refLocator,  
    CGopherConnection* pConnection);

 
CGopherFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrLocator,  
    DWORD dwLocLen,  
    DWORD_PTR dwContext);
```  
  
### <a name="parameters"></a>パラメーター  
 `hFile`  
 ハンドル、`HINTERNET`ファイルです。  
  
 `refLocator`  
 参照、[関数](../../mfc/reference/cgopherlocator-class.md)オブジェクトです。  
  
 `pConnection`  
 ポインター、[関数](../../mfc/reference/cgopherconnection-class.md)オブジェクトです。  
  
 `hSession`  
 現在のインターネット セッションへのハンドル。  
  
 `pstrLocator`  
 Gopher サーバーの検索に使用する文字列へのポインター。 参照してください[Gopher セッション](https://msdn.microsoft.com/library/24wz8xze.aspx)gopher ロケーターの詳細についてです。  
  
 *dwLocLen*  
 内のバイト数を含む DWORD`pstrLocator`します。  
  
 `dwContext`  
 開いているファイルのコンテキスト識別子へのポインター。  
  
### <a name="remarks"></a>コメント  
 必要があります、 `CGopherFile` gopher インターネット セッション中に、ファイルを読み取るオブジェクトです。  
  
 作成しないで、`CGopherFile`オブジェクトに直接します。 代わりに、 [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile)を gopher サーバー上のファイルを開きます。  
  
## <a name="see-also"></a>関連項目  
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [関数のクラス](../../mfc/reference/cgopherlocator-class.md)   
 [関数のクラス](../../mfc/reference/cgopherfilefind-class.md)   
 [関数のクラス](../../mfc/reference/cgopherconnection-class.md)

