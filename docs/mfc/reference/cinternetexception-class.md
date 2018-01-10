---
title: "CInternetException クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
dev_langs: C++
helpviewer_keywords:
- CInternetException [MFC], CInternetException
- CInternetException [MFC], m_dwContext
- CInternetException [MFC], m_dwError
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8caa275af4469d45672125677d960b71212fe3de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cinternetexception-class"></a>CInternetException クラス
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
|[CInternetException::m_dwContext](#m_dwcontext)|例外の原因となった操作に関連付けられているコンテキストの値です。|  
|[CInternetException::m_dwError](#m_dwerror)|例外の原因となったエラー。|  
  
## <a name="remarks"></a>コメント  
 `CInternetException`クラスには、次の 2 つのパブリック データ メンバーが含まれています。 この例外に関連付けられているエラー コードが格納されて 1 つと、エラーに関連付けられたインターネット アプリケーションのコンテキスト識別子を保持して、他のです。  
  
 インターネット アプリケーションのコンテキスト識別子の詳細については、記事を参照してください。 [wininet の基礎を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## <a name="requirements"></a>必要条件  
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
 MFC のグローバル関数を呼び出して、CInternetException をスローする[AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception)です。  
  
##  <a name="m_dwcontext"></a>CInternetException::m_dwContext  
 関連するインターネット操作に関連付けられているコンテキストの値です。  
  
```  
DWORD_PTR m_dwContext;  
```  
  
### <a name="remarks"></a>コメント  
 コンテキスト識別子が指定した[CInternetSession](../../mfc/reference/cinternetsession-class.md)に MFC によって渡されると[関数](../../mfc/reference/cinternetconnection-class.md)- と[CInternetFile](../../mfc/reference/cinternetfile-class.md)-クラスを派生します。 この既定の動作をオーバーライドして割り当てられた`dwContext`パラメーター独自の値。 `dwContext`指定したオブジェクトのすべての操作に関連付けられます。 `dwContext`によって返される操作のステータス情報を識別する[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)です。  
  
##  <a name="m_dwerror"></a>CInternetException::m_dwError  
 例外の原因となったエラー。  
  
```  
DWORD m_dwError;  
```  
  
### <a name="remarks"></a>コメント  
 このエラー値は、システム エラー コード、WINERROR で見つかりました。-H、または WININET からエラー値。H.  
  
 Win32 エラー コードの一覧は、次を参照してください。[エラーコード](http://msdn.microsoft.com/library/windows/desktop/ms681381)です。 インターネットに固有のエラー メッセージの一覧を参照してください。 どちらのトピックには、Windows SDK でです。  
  
## <a name="see-also"></a>参照  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)
