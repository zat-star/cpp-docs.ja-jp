---
title: "CGopherFile クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
dev_langs:
- C++
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce90eb2baf4ce8f6ba0136a9efd503086b686aa6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cgopherfile-class"></a>CGopherFile クラス
gopher サーバー上のファイルを検索し、読み込む機能が用意されています。  
  
> [!NOTE]
>  クラスは、 `CGopherConnection`、 `CGopherFile`、 `CGopherFileFind`、`CGopherLocator`し、Windows XP のプラットフォームでは機能しませんが、引き続き以前のプラットフォームで動作するため、そのメンバーが使用されなくなりました。  
  
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
 Gopher サービスには、ユーザーが情報を検索するためのメニュー駆動インターフェイスとして主にこのサービスが機能するため、gopher ファイルにデータを書き込むことはできません。 `CGopherFile`メンバー関数**書き込み**、 `WriteString`、および`Flush`は適用されていない`CGopherFile`です。 これらの関数を呼び出すことで、`CGopherFile`オブジェクトを返します、[行わない](../../mfc/reference/cnotsupportedexception-class.md)です。  
  
 方法の詳細について`CGopherFile`クラスでは、その他の MFC インターネット機能が、記事を参照して[wininet の基礎を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxinet.h  
  
##  <a name="cgopherfile"></a>CGopherFile::CGopherFile  
 このメンバー関数は構築するために、`CGopherFile`オブジェクト。  
  
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
 ハンドル、`HINTERNET`ファイル。  
  
 `refLocator`  
 参照、[関数](../../mfc/reference/cgopherlocator-class.md)オブジェクト。  
  
 `pConnection`  
 ポインター、[関数](../../mfc/reference/cgopherconnection-class.md)オブジェクト。  
  
 `hSession`  
 現在のインターネット セッションへのハンドル。  
  
 `pstrLocator`  
 Gopher サーバーを検索に使用する文字列へのポインター。 参照してください[Gopher セッション](cgopherlocator-class.md)gopher ロケーターの詳細についてはします。  
  
 *dwLocLen*  
 内のバイト数を含む DWORD`pstrLocator`です。  
  
 `dwContext`  
 開いているファイルのコンテキスト識別子へのポインター。  
  
### <a name="remarks"></a>コメント  
 必要があります、 `CGopherFile` gopher インターネット セッション中に、ファイルから読み取るオブジェクト。  
  
 作成することはありません、`CGopherFile`オブジェクトに直接できます。 代わりに、 [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile)を gopher サーバー上のファイルを開きます。  
  
## <a name="see-also"></a>参照  
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [関数クラス](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)   
 [CGopherConnection クラス](../../mfc/reference/cgopherconnection-class.md)
