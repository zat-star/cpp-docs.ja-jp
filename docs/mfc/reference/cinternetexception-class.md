---
title: "クラスを表す |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
dev_langs:
- C++
helpviewer_keywords:
- exception handling, Internet operations
- exceptions, Internet
- CInternetException class
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: a128095cfc443f0ea8de4cb4028b903929a83f47
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetexception-class"></a>表すクラス
インターネット操作に関する例外条件を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CInternetException : public CException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetException::CInternetException](#cinternetexception)|`CInternetException` オブジェクトを構築します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetException::m_dwContext](#m_dwcontext)|例外の原因となった操作に関連付けられたコンテキスト値です。|  
|[CInternetException::m_dwError](#m_dwerror)|例外の原因となったエラー。|  
  
## <a name="remarks"></a>コメント  
 `CInternetException`クラスには、2 つのパブリック データ メンバーが含まれています。 例外に関連付けられているエラー コードが格納されて&1; つと、エラーに関連付けられているインターネット アプリケーションのコンテキスト識別子を保持して、もう一方です。  
  
 インターネット アプリケーションのコンテキスト識別子の詳細については、記事を参照してください。 [WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="cinternetexception"></a>CInternetException::CInternetException  
 このメンバー関数が呼び出されます、`CInternetException`オブジェクトを作成します。  
  
```  
CInternetException(DWORD dwError);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwError`  
 例外の原因となったエラー。  
  
### <a name="remarks"></a>コメント  
 表すをスローするには、MFC のグローバル関数を呼び出して[AfxThrowInternetException](http://msdn.microsoft.com/library/c9645b10-9541-48b2-8b0c-94ca33fed3cb)します。  
  
##  <a name="m_dwcontext"></a>CInternetException::m_dwContext  
 関連するインターネット操作に関連付けられているコンテキストの値です。  
  
```  
DWORD_PTR m_dwContext;  
```  
  
### <a name="remarks"></a>コメント  
 コンテキスト識別子が指定した[CInternetSession](../../mfc/reference/cinternetsession-class.md) MFC に渡し、[関数](../../mfc/reference/cinternetconnection-class.md)- および[CInternetFile](../../mfc/reference/cinternetfile-class.md)-クラスを派生します。 この既定の設定をオーバーライドしていずれかを割り当てる`dwContext`パラメーター独自の値。 `dwContext`指定したオブジェクトのすべての操作に関連付けられます。 `dwContext`によって返される操作のステータス情報を識別する[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)します。  
  
##  <a name="m_dwerror"></a>CInternetException::m_dwError  
 例外の原因となったエラー。  
  
```  
DWORD m_dwError;  
```  
  
### <a name="remarks"></a>コメント  
 このエラー値は、システム、WINERROR で見つかったエラー コード。H、または WININET からエラー値。H.  
  
 Win32 エラー コードの一覧は、次を参照してください。[エラーコード](http://msdn.microsoft.com/library/windows/desktop/ms681381)します。 インターネットに固有のエラー メッセージの一覧を参照してください。 両方のトピックは、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)

