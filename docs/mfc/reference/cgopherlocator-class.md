---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
dev_langs:
- C++
helpviewer_keywords:
- gopher locator
- CGopherLocator class
- Internet, gopher searches
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
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
ms.openlocfilehash: c5c9b862714d046bc81a49dda27fd5fc062b9ba8
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherlocator-class"></a>関数のクラス
Gopher サーバーから、gopher「ロケーター」を取得、ロケーターの種類を決定およびロケーターを使用できるように[関数](../../mfc/reference/cgopherfilefind-class.md)します。  
  
> [!NOTE]
>  クラスは、 `CGopherConnection`、 `CGopherFile`、 `CGopherFileFind`、`CGopherLocator`し、Windows XP のプラットフォームで機能しませんが、以前のプラットフォームで動作し続けますので、そのメンバーは廃止されました。  
  
## <a name="syntax"></a>構文  
  
```  
class CGopherLocator : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CGopherLocator::CGopherLocator](#cgopherlocator)|`CGopherLocator` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CGopherLocator::GetLocatorType](#getlocatortype)|Gopher ロケーターを解析し、その属性を決定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CGopherLocator::operator LPCTSTR](#operator_lpctstr)|格納される文字に直接アクセスする、`CGopherLocator`オブジェクトを C スタイルの文字列として。|  
  
## <a name="remarks"></a>コメント  
 アプリケーションは、そのサーバーから情報を取得できる前に、gopher サーバーのロケーターを取得する必要があります。 ロケーターがある場合、不明確なトークンとしてロケーターを扱うその必要があります。  
  
 各 gopher ロケーターには、ファイルまたはサーバーの種類を決定する属性があります。 参照してください[GetLocatorType](#getlocatortype) gopher ロケーターの種類の一覧にします。  
  
 アプリケーションは、呼び出しのために、ロケーターを使用する通常[CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile)を特定の情報を取得します。  
  
 方法について説明する`CGopherLocator`他のインターネットの MFC クラスと動作は、記事を参照して[WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGopherLocator`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="cgopherlocator"></a>CGopherLocator::CGopherLocator  
 このメンバー関数を呼び出して作成する、`CGopherLocator`オブジェクトです。  
  
```  
CGopherLocator(const CGopherLocator& ref);
```  
  
### <a name="parameters"></a>パラメーター  
 `ref`  
 定数への参照を`CGopherLocator`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 作成しないで、`CGopherLocator`直接オブジェクトです。 代わりに、 [CGopherConnection::CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator)を作成してへのポインターを返す、`CGopherLocator`オブジェクトです。  
  
##  <a name="getlocatortype"></a>CGopherLocator::GetLocatorType  
 ロケーターの種類を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetLocatorType(DWORD& dwRef) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *dwRef*  
 参照、`DWORD`ロケーターの種類を受信します。 参照してください**解説**ロケーターの種類のテーブルにします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 種類は次のとおりです。  
  
|値|説明|  
|-----------|-------------|  
|GOPHER_TYPE_TEXT_FILE|ASCII テキスト ファイル。|  
|GOPHER_TYPE_DIRECTORY|Gopher 項目が追加のディレクトリ。|  
|GOPHER_TYPE_CSO|CSO 電話帳サーバーです。|  
|GOPHER_TYPE_ERROR|エラー状態を示します。|  
|GOPHER_TYPE_MAC_BINHEX|BINHEX 形式で Macintosh ファイルです。|  
|GOPHER_TYPE_DOS_ARCHIVE|DOS のアーカイブ ファイルです。|  
|GOPHER_TYPE_UNIX_UUENCODED|エンコードされていないファイルです。|  
|GOPHER_TYPE_INDEX_SERVER|インデックス サーバーです。|  
|GOPHER_TYPE_TELNET|Telnet サーバーです。|  
|GOPHER_TYPE_BINARY|バイナリ ファイルです。|  
|GOPHER_TYPE_REDUNDANT|重複しているサーバー。 含まれる情報は、プライマリ サーバーの複製です。 プライマリ サーバーは、GOPHER_TYPE_REDUNDANT 型がない最後のディレクトリ エントリです。|  
|GOPHER_TYPE_TN3270|TN3270 サーバーです。|  
|GOPHER_TYPE_GIF|GIF のグラフィックス ファイルです。|  
|GOPHER_TYPE_IMAGE|イメージ ファイル。|  
|GOPHER_TYPE_BITMAP|ビットマップ ファイルです。|  
|GOPHER_TYPE_MOVIE|ムービー ファイルです。|  
|GOPHER_TYPE_SOUND|サウンド ファイルです。|  
|GOPHER_TYPE_HTML|HTML ドキュメント。|  
|GOPHER_TYPE_PDF|PDF ファイルです。|  
|GOPHER_TYPE_CALENDAR|予定表ファイルです。|  
|GOPHER_TYPE_INLINE|インライン ファイル。|  
|GOPHER_TYPE_UNKNOWN|項目の種類が不明です。|  
|GOPHER_TYPE_ASK|Ask + アイテムです。|  
|GOPHER_TYPE_GOPHER_PLUS|Gopher + アイテムです。|  
  
##  <a name="operator_lpctstr"></a>CGopherLocator::operator LPCTSTR  
 このキャスト演算子に含まれる、null で終わる C 文字列にアクセスするための効率的な方法を提供する、`CGopherLocator`オブジェクトです。  
  
```  
operator LPCTSTR () const;  
```  
  
### <a name="return-value"></a>戻り値  
 文字列のデータを指すポインター。  
  
### <a name="remarks"></a>コメント  
 文字はコピーされません。ポインターのみが返されます。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/cgopherfilefind-class.md)

